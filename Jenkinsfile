import com.cloudbees.plugins.credentials.Credentials
import com.cloudbees.hudson.plugins.folder.properties.FolderCredentialsProvider.FolderCredentialsProperty
import com.cloudbees.hudson.plugins.folder.AbstractFolder
import com.cloudbees.hudson.plugins.folder.Folder
import com.cloudbees.plugins.credentials.impl.*
import com.cloudbees.plugins.credentials.*
import com.cloudbees.plugins.credentials.domains.*

pipeline{
    agent any
    stages{
        stage('print-initial'){
            steps{
                printCreds()
            }
        }
        stage('create-new-cred'){
            steps{
                //createNewCred("JenkisfileTest")
                println("This is where we would create a new credential to test with.")
            }
        }
        stage('print-final'){
            steps{
                printCreds()
            }
        }
    }
}

def printCreds(){
    Set<Credentials> allCredentials = new HashSet<Credentials>();
    
    def creds = com.cloudbees.plugins.credentials.CredentialsProvider.lookupCredentials(
        com.cloudbees.plugins.credentials.Credentials.class
    );
    
    allCredentials.addAll(creds)
    
    Jenkins.instance.getAllItems(com.cloudbees.hudson.plugins.folder.Folder.class).each{ f ->
        println(f.name)
        creds = com.cloudbees.plugins.credentials.CredentialsProvider.lookupCredentials(
            com.cloudbees.plugins.credentials.Credentials.class, f)
        for (c in creds) {
           println(c.id + ": " + c.description)
        }
        allCredentials.addAll(creds)
    }
    for (c in allCredentials) {
       println(c.id + ": " + c.description)
    }
}

def createNewCred( String folderName){
    String id = UUID.randomUUID().toString()
    Credentials c = new UsernamePasswordCredentialsImpl(CredentialsScope.GLOBAL, id, "description:"+id, "user", "password")
    println "New Credential" + c.toString()

Jenkins.instance.getAllItems(Folder.class)
    .findAll{it.name.equals(folderName)}
    .each{
        AbstractFolder<?> folderAbs = AbstractFolder.class.cast(it)
        FolderCredentialsProperty property = folderAbs.getProperties().get(FolderCredentialsProperty.class)
        if(property != null){
            property.getStore().addCredentials(Domain.global(), c)
            println "Credentials for the folder" + property.getCredentials().toString()
        }
    }
}
