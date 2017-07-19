---
title: "Publicaci&#243;n de servicio WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Publicaci&#243;n de servicio WCF
La publicación de servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ayuda a pasar del entorno de desarrollo preliminar que proporciona el host de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y el cliente de prueba de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a la implementación real de la aplicación en un entorno producción con fines de prueba.  Antes de confirmar un plan de implementación final, puede usar la publicación de servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] para comprobar que el servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] funciona correctamente y está listo para su publicación.  También puede decidir implementar las bibliotecas de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en varias ubicaciones de destino para comprobarlas.  
  
## Ubicaciones de destino y servicios compatibles  
 La publicación de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] permite publicar servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] creados a partir del conjunto de plantillas de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y sus plantillas de elementos correspondientes, que son las siguientes:  
  
-   Plantilla de biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con plantilla de elementos.  
  
-   Plantilla de biblioteca de servicio de flujo de trabajo secuencial con plantilla de elementos.  
  
-   Plantilla de biblioteca de servicio de flujo de trabajo de máquina de estado con plantilla de elementos.  
  
-   Biblioteca de servicio de distribución.  
  
 Para encontrar estas plantillas de servicio, elija **Archivo** \-\> **Nuevo proyecto** \-\> **Visual Basic** o **Visual C\#** \-\> **WCF**.  
  
 El servicio se puede publicar en las ubicaciones de destino siguientes.  
  
-   IIS local.  
  
-   Sistema de archivos.  
  
-   Sitio FTP.  
  
-   Sitio remoto.  
  
## Uso de la publicación de servicios de WCF  
 Para llevar a cabo una implementación de servicio, realice los siguientes pasos:  
  
1.  Abra Visual Studio con privilegios elevados \(haga clic con el botón secundario en el archivo ejecutable y use "Ejecutar como administrador" para iniciarlo\).  Si usa IIS 7.0 o una versión posterior, asegúrese de que ha instalado el componente "Metabase de IIS y Compatibilidad de configuración de IIS 6" a través de la opción "Activar o desactivar las características de Windows" del Panel de control.  
  
2.  Abra un proyecto de servicio, seleccione **Compilar**\-\>**Publicar \<Nombre de proyecto\>** en el menú principal o haga clic con el botón secundario en el **Explorador de soluciones** y haga clic en  **Publicar**.  
  
3.  Se muestra la ventana **Publicar**.  Haga clic en **…**.  para especificar la ubicación de destino en la que se debe implementar el servicio.  Puede decidir implementar la aplicación en el servidor IIS local, en el sistema de archivos, en un sitio FTP o en un sitio remoto.  Si va a implementar la aplicación en IIS local, puede seleccionar su sitio web y crear su aplicación web bajo este haciendo clic en el icono **Crear nueva aplicación web** en la esquina superior derecha.  
  
4.  Después de hacer clic en **Publicar** en la ventana principal, Visual Studio implementa la aplicación en la ubicación de destino especificada y copia los archivos Web.config, .svc y de ensamblado en el directorio de destino.  .  El nombre de .svc será "ProjectName.ServiceName.svc".  Una vez publicado el servicio correctamente, puede encontrar un enlace activo en la ventana de salida de Visual Studio, que será similar a "Conectando con http:\/\/localhost\/WebApplicationFolderName ...".  Puede presionar CTRL y hacer clic el vínculo para abrir una página del explorador dentro de Visual Studio y ver la estructura de directorios del servicio.  
  
     Si no puede ir al sitio, puede que sea porque el explorador de directorios no está habilitado en IIS.  Siga las sugerencias de la sección "Cosas que puede probar" para habilitarlo.  Alternativamente, puede escribir directamente "http:\/\/localhost\/WebApplicationFolderName\/ProjectName.ServiceName.svc" para ver su página de servicio.  
  
 Puede usar la ventana **Publicar** para especificar si desea copiar el archivo de ensamblado, de configuración y .svc de todos los servicios definidos en el proyecto en la ubicación de destino y sobrescribir los archivos existentes en el destino.  
  
 Si decide implementar su aplicación en IIS local, puede encontrar errores relacionados con la instalación de IIS.  Asegúrese de que IIS se instale correctamente.  Puede escribir "http:\/\/localhost" en su explorador y comprobar si aparece la página predeterminada de IIS.  En algunos casos, los problemas pueden deberse también a un registro incorrecto de ASP.NET o [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en IIS.  Puede abrir el símbolo del sistema de Visual Studio y ejecutar el comando "aspnet\_regiis.exe \- ir" para corregir los problemas de registro de ASP.NET, o bien ejecutar el comando "ServiceModelReg.exe .ia" para corregir los problemas de registro de WCF.  
  
## Archivos generados para publicación  
 Antes de que una biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se pueda hospedar en Web, la herramienta genera los archivos siguientes: los archivos de ensamblado, el archivo Web.config y el archivo .svc.  Todos los archivos se copian en la ubicación de destino.  A continuación se publica el servicio.  
  
### Archivos de ensamblado  
 Al publicar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con esta herramienta, primero se crea el servicio automáticamente y, después, se generan los archivos de ensamblado en el proyecto de servicio.  
  
### Archivo .SVC  
 La operación de publicación genera un archivo \*.svc para cada servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], exista o no el archivo, para garantizar la validez de la versión.  Hay dos tipos de archivos svc diferentes: uno para la biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y la biblioteca de servicio de distribución, y otro para la biblioteca de servicio de flujo de trabajo secuencial y de máquina de estado.  El archivo \*.svc generado se copia en la carpeta raíz de la ubicación de destino.  
  
### Archivo Web.config  
 Cada vez que un proyecto de servicio se publica en una ubicación de destino concreta, se crea un archivo Web.config.  
  
 El archivo Web.config generado incluye secciones web que son útiles para el hospedaje en Web y el contenido de App.config para la biblioteca de servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], con los cambios siguientes:  
  
-   Se excluye la dirección base.  
  
-   La configuración del elemento `<diagnostics>` se excluye para conservar la configuración de seguimiento de la plataforma de destino.  
  
## Publicación de servicios WCF con enlaces que no son HTTP en IIS  
 Si está utilizando IIS7.0 o una versión posterior, puede publicar servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con enlaces no HTTP en IIS.  Necesita realizar algunas tareas de configuración previa.  Para obtener más información, vea los temas de [Hospedaje en Servicio de activación de procesos de Windows](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
## Seguridad  
 Para la publicación en el servidor IIS local se requieren privilegios de administrador, porque IIS debe ejecutarse con la cuenta Administrador.  Si un usuario sin privilegios de administrador inicia la publicación de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], IIS no estará disponible como ubicación de destino.  La publicación en el sistema de archivos, en un sitio FTP o en un sitio remoto funciona sin privilegios de administrador.  
  
## Vea también  
 [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)   
 [Host de servicio WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)   
 [Cliente de prueba de WCF \(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)