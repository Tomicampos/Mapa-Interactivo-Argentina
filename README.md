Despliegue de Aplicación en Kubernetes usando AWS EKS
Este repositorio contiene los archivos necesarios para desplegar una aplicación en Kubernetes utilizando AWS EKS. La aplicación es un mapa interactivo que se sirve a través de un contenedor Docker.

Requisitos Previos
para comenzar debes tener instalado lo siguiente:

Docker: Para construir y gestionar contenedores.
kubectl: Para interactuar con clústeres Kubernetes.
AWS CLI: Para configurar credenciales y gestionar recursos en AWS.
Git: Para clonar este repositorio.

Configuración Inicial
1- Configuración de AWS CLI:
  
  "aws configure"

Ingresa tus credenciales de AWS proporcionadas por el administrador en caso de no serlo. Esto configura las credenciales necesarias para gestionar recursos en AWS.

2- Configuración de kubectl:
Asegúrate de tener un archivo kubeconfig configurado para acceder a tu clúster de AWS EKS. 

Archivos de Configuración
deployment.yaml: Este archivo describe cómo se debe desplegar la aplicación en el clúster de Kubernetes, especificando la imagen del contenedor y el número de réplicas.
deploy.yaml (GitHub Actions): Este archivo configura un pipeline de GitHub Actions para construir y desplegar automáticamente la aplicación en Kubernetes cuando se realiza un push al repositorio (en esta caso a la rama desa)

Acceso a la Aplicación: Una vez desplegada la aplicación, puedes acceder a ella a través del servicio LoadBalancer de AWS EKS con el comando "kubectl get svc mapa-interactivo-service --namespace=nombredelnamespace", copiando la direccion IP externa y pegandola en el navegador. 



