pipeline{
agent any
stages{
stage('checkout'){
steps{
git url:'https://github.com/ramakrishnanyadav/docker-b4.git',branch:'main'
}
}

stage('build Image'){
steps{
bat 'docker build -t mywebsite . '
}
}
}

stage('stop old containers'){
steps{
bat 'docker stop mycont || exit 0'
bat 'docker rm mycont  || exit 0'
}
}

stage('Run Image - containerize'){
steps{
bat'docker run -d -p 7000:80 --name mycont  mywebsite'
}
}
}
