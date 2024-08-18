pipeline
{
    agent any
    tools 
    {
        maven 'maven'
    }
    stages
    {
        stage("checkout")
        {
           steps
           {
               git'https://github.com/Munisupriya/codes.git'
           }
        }
        stage("compile")
         {
           steps
           {
               sh 'mvn compile'
           }
         }
        
        stage("package")
        {
            steps
            {
                sh 'mvn package -DskipTests'
            }
        }
        stage("image")
        {
            steps
            {
                sh 'docker build -t myfile .'
            }
        }
    
    }
}
    
   
