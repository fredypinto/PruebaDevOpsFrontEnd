# PruebaDevOpsFrontEnd
1. CI:
se integro el codigo fuente con la herramienta AzureDevOps, alli lo que se hizo fue:
 - crear el pipeline de integracion continua, mediante una serie de tarea generar un artefacto o entrgable para su despliegue.
 el archivo del pipeline se encuentra en la siguente ruta [pipelineCIyml](https://github.com/fredypinto/PruebaDevOpsFrontEnd/blob/main/azure-pipelines.yml)
 
2. CD:
 - configurar la maquina docker para el despliegue de la aplicacion
 - construir archivos Dockerfile y docker-compose para la compilacion y despliego de la imagen:
     . la configuracion del Dockerfile es:
       - como base nginx
       - copia los archivos generados por CI a la ruta html de nginx
       - arranca el servidor nginx
     . la configuracion del docker-compose:
      - se define el servicio 
      - nombre de contenedor
      - nombre de la imagen con la cual correra el contenedor
      - puertos
     . los arvhivos estan en la sigueinte ruta: [Archivos-docker](https://github.com/fredypinto/PruebaDevOpsFrontEnd/tree/main/Dockerfile)
 - crear el pipeline de despliegue, en donde mediante conexion via ssh el pipeline copia los artefactos generados por CI y seguido compila la imagen y despliega el  contenedor, tambien se agrego una stage mas para realizar el despliegue en k8s.
 