MINI MANUAL DESCRIPTIVO JDAG
1. **Conceptos básicos sobre contenedores:**
   - Los **contenedores** son unidades de software que encapsulan una aplicación y sus dependencias, permitiendo que se ejecuten de manera consistente en diferentes entornos.
   - **Docker** es una herramienta popular para crear, distribuir y ejecutar contenedores.
   - **Kubernetes** es una plataforma de orquestación de contenedores que facilita la administración y escalabilidad de aplicaciones en contenedores.

2. **Pasos generales para desplegar un servicio en un contenedor:**
   - **Crea una imagen del contenedor:**
     - Define un archivo `Dockerfile` que especifique cómo construir la imagen del contenedor.
     - Utiliza el comando `docker build` para crear la imagen.
   - **Ejecuta un contenedor a partir de la imagen:**
     - Utiliza el comando `docker run` para iniciar un contenedor basado en la imagen creada.
     - Especifica puertos, volúmenes y otras configuraciones según tus necesidades.
   - **Despliega en un servidor de producción:**
     - Configura un servidor de producción con Docker instalado.
     - Copia la imagen del contenedor al servidor (puedes usar `docker save` y `docker load`).
     - Ejecuta el contenedor en el servidor utilizando el mismo comando `docker run`.

3. **Ejemplo con AWS Fargate:**
   - AWS Fargate es un servicio de AWS que permite ejecutar contenedores sin preocuparse por la infraestructura subyacente.
   - Puedes seguir este [tutorial de AWS](https://aws.amazon.com/es/blogs/aws-spanish/aprende-a-desplegar-aplicaciones-en-contenedores-serverless-con-aws/) para desplegar tu primer contenedor en AWS utilizando Fargate¹.
   - En resumen:
     - Crea una imagen de Docker para tu aplicación.
     - Carga la imagen en Amazon Elastic Container Registry (ECR).
     - Crea una definición de tarea en Amazon ECS que apunte a la imagen de ECR.
     - Configura un servicio de ECS para ejecutar la tarea en Fargate.

Recuerda que cada plataforma y proveedor de servicios en la nube puede tener sus propias particularidades, pero estos pasos generales te darán una idea de cómo desplegar un servicio en un contenedor para un servidor de producción. ¡Buena suerte! 🚀¹

REFERENCIAS PARA MAS INFO =)
(1) Aprende a desplegar aplicaciones en contenedores serverless con AWS .... https://aws.amazon.com/es/blogs/aws-spanish/aprende-a-desplegar-aplicaciones-en-contenedores-serverless-con-aws/.
(2) Despliegue de un servicio web al contenedor de servicios web del ... - IBM. https://bing.com/search?q=desplegar+servicio+en+contenedor+servidor+producci%c3%b3n.
(3) Despliegue de un servicio web al contenedor de servicios web del ... - IBM. https://www.ibm.com/docs/es/mam/7.6.0.8?topic=services-deploying-web-service-product-web-service-container.
(4) Cómo desplegar contenedores en Docker - Platzi. https://platzi.com/blog/desplegar-contenedores-docker/.
(5) Contenedores y Orquestación: Transformando la Gestión de ... - Medium. https://medium.com/@villamorosjuan/contenedores-y-orquestaci%C3%B3n-transformando-la-gesti%C3%B3n-de-aplicaciones-en-producci%C3%B3n-0f2ebbd8aac5.
































# Telematica
En el shell de AWS instalar terraform:
git clone https://github.com/tfutils/tfenv.git ~/.tfenv
mkdir ~/bin
ln -s ~/.tfenv/bin/* ~/bin/
tfenv install 1.8.1
tfenv use 1.8.1
terraform --version

Descargar los scripts de terraform:
git clone https://github.com/JDAG-SUP/ULTIMA-NOTA-TELEMATICA

Ejecutar terraform para aplicar la configuración:
terraform init
terraform apply

Escribir yes para aplicar y copiar la ip publica dada para acceder al sitio (esperar que el servidor inicie).

Ingresar al servidor y ejecutar los siguientes comandos:
cd /Telematica
sudo docker build -t web-image:v1 .
sudo docker run -d -p 8080:80 web-image:v1
