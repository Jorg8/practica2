pipeline {
	agent any
	tools {
		jdk 'java'
		maven 'maven'
	}
	stages {
		stage('Inicio') {
			steps {
				echo 'Bienvenido'
			}
		}
		stage('Pruebas') {
			steps {
				echo 'Ejecución de pruebas unitarias'
				sh 'mvn test'
			}
		}
		stage('Empaquetado') {
			steps {
				echo 'Empaquetado de la aplicación'
				sh 'mvn package'
			}
		}
		stage('Ejecución') {
			steps {
				echo 'Ejecutando el paquete'
				sh 'mvn exec:java -Dexec.mainClass="es.ibermatica.jenkins.App"'
			}
		}
	}
	post {
		always {
			echo 'El buid ha terminado'
		}
		success {
			echo 'Build correcto'
		}
		failure {
			echo 'El build ha fallado'
		}
	}
}
