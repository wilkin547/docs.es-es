---
title: Publicación de servicio WCF
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 33725c2f393529a7e59ed0b3ae1db01a359fb9a5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299727"
---
# <a name="wcf-service-publishing"></a>Publicación de servicio WCF

Publicación de servicios de Windows Communication Foundation (WCF) le ayuda a pasar del entorno de desarrollo preliminar ofrecido por Host de servicio WCF y el cliente de prueba WCF para implementar realmente la aplicación en un entorno de producción con fines de prueba. Antes de comprometerse a un plan de implementación final, puede usar la publicación de servicios de Windows Communication Foundation (WCF) para comprobar que el servicio WCF se realice correctamente y está listo para publicarse. También puede implementar las bibliotecas de servicio WCF en varias ubicaciones de destino para las pruebas.

## <a name="supported-services-and-target-locations"></a>Ubicaciones de destino y servicios compatibles

Publicación de servicios de WCF admite la publicación de servicios WCF creado desde el conjunto de plantillas de biblioteca de servicio WCF y sus plantillas de elemento correspondientes, que incluyen las siguientes:

-   Plantilla de biblioteca de servicios WCF con la plantilla de elemento.

-   Biblioteca de servicio de distribución.

Puede encontrar estas plantillas de servicio, elija **archivo** > **nuevo proyecto** > [**Visual Basic** o **Visual C#** ] > **WCF**. Para otras plantillas WCF en esta ubicación (incluida la aplicación de servicio de flujo de trabajo de WCF y la aplicación de servicio WCF), puede publicar mediante [para aplicaciones web de publicación de un solo clic](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110)).

El servicio se puede publicar en las ubicaciones de destino siguientes.

-   IIS local.

-   Sistema de archivos.

-   Sitio FTP.

## <a name="using-wcf-service-publishing"></a>Uso de la publicación de servicios de WCF

Para llevar a cabo una implementación de servicio, realice los siguientes pasos:

1. Abra Visual Studio con privilegios elevados (haga clic en el archivo ejecutable y elija **ejecutar como administrador** para abrirlo).  Si está utilizando IIS 7.0 o versiones posteriores, asegúrese de que ha instalado el componente "IIS compatibilidad con la Metabase y IIS6 Configuration" con "Windows activar o desactivar las características" en el Panel de Control.

2. Abra un proyecto de servicio, seleccione **compilar** > **publicar \<nombre del proyecto >** en el menú principal, o haga clic en el proyecto en **el Explorador de soluciones**y haga clic en **publicar**.

3. El **publicar** aparecerá la ventana. Haga clic en el **...** . para especificar la ubicación de destino en la que se debe implementar el servicio. Puede seleccionar para implementar la aplicación en IIS local, sistema de archivos o sitio FTP. Si implementa la aplicación en IIS local, puede seleccionar el sitio Web y crear la aplicación web en ella, haciendo clic en el **crear nueva aplicación Web** situado en la esquina superior derecha.

4. Tras hacer clic en **publicar** en la ventana principal, Visual Studio implementa la aplicación en la ubicación de destino especificado y copia los archivos Web.config, .svc y de ensamblado en el directorio de destino. . El nombre de .svc será "ProjectName.ServiceName.svc". Una vez publicado el servicio correctamente, puede encontrar un vínculo rápido en la ventana de salida de Visual Studio, que es similar a "conectarse a `http://localhost/WebApplicationFolderName...`". Puede presionar CTRL y hacer clic el vínculo para abrir una página del explorador dentro de Visual Studio y ver la estructura de directorios del servicio.

     Si no puede ir al sitio, puede que sea porque el explorador de directorios no está habilitado en IIS. Siga las sugerencias en la sección "Cosas que puede probar" para habilitarla. Como alternativa, puede escribir directamente `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc` para ver su página de servicio.

Puede usar **publicar** para especificar si desea copiar el ensamblado, la configuración y el archivo .svc para todos los servicios definidos en el proyecto para la ubicación de destino y sobrescribir archivos existentes en el destino.

Si decide implementar su aplicación en IIS local, puede encontrar errores relacionados con la instalación de IIS. Asegúrese de que IIS se instale correctamente. Puede escribir `http://localhost` en el Explorador de la barra de direcciones y compruebe si la página predeterminada IIS muestra. En algunos casos, los problemas también pueden deberse a un registro incorrecto de ASP.NET o WCF en IIS. Puede abrir el símbolo del sistema para desarrolladores de Visual Studio y ejecute el comando `aspnet_regiis.exe -ir` para solucionar problemas de registro ASP.NET o ejecute el comando `ServiceModelReg.exe –ia` para solucionar problemas de registro WCF.

## <a name="files-generated-for-publishing"></a>Archivos generados para publicación
 Antes de que puede ser una biblioteca de servicios WCF hospedados en Web, la herramienta genera los siguientes archivos: archivos de ensamblado, el archivo Web.config y el archivo .svc. Todos los archivos se copian en la ubicación de destino. A continuación se publica el servicio.

### <a name="assembly-files"></a>Archivos de ensamblado
 Al publicar un servicio WCF con esta herramienta, el servicio se crea automáticamente en primer lugar y se generan los archivos de ensamblado en el proyecto de servicio después de compilar.

### <a name="svc-file"></a>Archivo .SVC
 La operación de publicación genera un archivo *.svc para cada servicio WCF, si el archivo existe o no, para garantizar la validez de la versión. Hay dos tipos de archivos svc diferentes: uno para la biblioteca de servicios WCF y biblioteca de servicio de distribución y otro para secuencial y de biblioteca de servicio de flujo de trabajo de equipo de estado. Generado \*archivo .svc se copia en la carpeta raíz en la ubicación de destino.

### <a name="webconfig-file"></a>Archivo Web.config
 Cada vez que un proyecto de servicio se publica en una ubicación de destino concreta, se crea un archivo Web.config.

 El archivo Web.config generado incluye secciones Web que son útiles para el hospedaje Web y el contenido de App.config de la biblioteca de servicios WCF con los cambios siguientes:

-   Se excluye la dirección base.

-   La configuración del elemento `<diagnostics>` se excluye para conservar la configuración de seguimiento de la plataforma de destino.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Publicación de servicios WCF con enlaces que no son HTTP en IIS
 Si está utilizando IIS7.0 o versiones posteriores, puede publicar servicios WCF con enlaces que no son HTTP en IIS. Necesita realizar algunas tareas de configuración previa. Para obtener más información, vea los temas de [hospedaje en Windows Process Activation Service](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Seguridad
 Para la publicación en el servidor IIS local se requieren privilegios de administrador, porque IIS debe ejecutarse con la cuenta Administrador. Si un usuario sin privilegios de administrador abre la publicación de servicios de WCF, IIS no está disponible como una ubicación de destino. Publicación en el sistema de archivos o el sitio FTP funciona sin privilegios de administrador.

## <a name="see-also"></a>Vea también

- [Plantillas de Visual Studio para WCF](../../../docs/framework/wcf/wcf-vs-templates.md)
- [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)