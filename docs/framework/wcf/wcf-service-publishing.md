---
title: Publicación de servicio WCF
description: La publicación de servicios WCF le ayuda a implementar la aplicación en un entorno de producción con fines de prueba.
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 99798b75e1dc01c8db361f4d8d1f162c7f7617b1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245679"
---
# <a name="wcf-service-publishing"></a>Publicación de servicio WCF

La publicación de servicios de Windows Communication Foundation (WCF) le ayuda a progresar desde el entorno de desarrollo temprano proporcionado por el host de servicio de WCF y el cliente de prueba de WCF para implementar realmente la aplicación en un entorno de producción con fines de prueba. Antes de confirmar un plan de implementación final, puede usar la publicación de servicio Windows Communication Foundation (WCF) para comprobar que el servicio WCF funciona correctamente y está listo para publicarse. También puede optar por implementar las bibliotecas de servicio de WCF en varias ubicaciones de destino para las pruebas.

## <a name="supported-services-and-target-locations"></a>Ubicaciones de destino y servicios compatibles

La publicación de servicios WCF admite la publicación de servicios WCF creados a partir del conjunto de plantillas de biblioteca de servicios WCF y sus plantillas de elementos correspondientes, entre las que se incluyen las siguientes:

- Plantilla de biblioteca de servicio WCF con plantilla de elementos.

- Biblioteca de servicio de distribución.

Para encontrar estas plantillas de servicio, elija **archivo**  >  **nuevo proyecto** > [**Visual Basic** o **Visual C#**] > **WCF**. Para otras plantillas WCF en esta ubicación (incluida la aplicación de servicio de flujo de trabajo WCF y la aplicación de servicio WCF), puede publicar mediante la [publicación con un solo clic para aplicaciones web](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110)).

El servicio se puede publicar en las ubicaciones de destino siguientes.

- IIS local.

- Sistema de archivos.

- Sitio FTP.

## <a name="using-wcf-service-publishing"></a>Uso de la publicación de servicios de WCF

Para llevar a cabo una implementación de servicio, realice los siguientes pasos:

1. Abra Visual Studio con privilegios elevados (haga clic con el botón derecho en el archivo ejecutable y elija **Ejecutar como administrador** para abrirlo).  Si usa IIS 7,0 o posterior, asegúrese de que ha instalado el componente "compatibilidad con la configuración de la metabase de IIS y IIS6" con "activar o desactivar las características de Windows" en el panel de control.

2. Abra un proyecto de servicio, seleccione **compilar**  >  ** \<Project Name> publicación** en el menú principal, o haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y haga clic en **publicar**.

3. Aparece la ventana **publicar** . Haga clic en **..**.. para especificar la ubicación de destino en la que se debe implementar el servicio. Puede seleccionar la implementación de la aplicación en el sitio de IIS, sistema de archivos o FTP local. Si va a implementar la aplicación en el IIS local, puede seleccionar el sitio web y crear su aplicación web bajo él; para ello, haga clic en el icono **crear nueva aplicación web** en la esquina superior derecha.

4. Después de hacer clic en **publicar** en la ventana principal, Visual Studio implementa la aplicación en la ubicación de destino especificada y copia los archivos de Web.config,. SVC y de ensamblado en el directorio de destino. . El nombre de. SVC será "ProjectName. ServiceName. SVC". Una vez que el servicio se publique correctamente, puede encontrar un modo de impresión en la ventana de salida de Visual Studio, que es similar a "conectando `http://localhost/WebApplicationFolderName...` ". Puede presionar CTRL y hacer clic el vínculo para abrir una página del explorador dentro de Visual Studio y ver la estructura de directorios del servicio.

     Si no puede ir al sitio, puede que sea porque el explorador de directorios no está habilitado en IIS. Siga las sugerencias de la sección "cosas que puede probar" para habilitarla. También puede escribir directamente `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc` para ver la página de servicio.

Puede usar **publicar** para especificar si desea copiar el ensamblado, la configuración y el archivo. SVC para todos los servicios definidos en el proyecto en la ubicación de destino y sobrescribir los archivos existentes en el destino.

Si decide implementar su aplicación en IIS local, puede encontrar errores relacionados con la instalación de IIS. Asegúrese de que IIS se instale correctamente. Puede escribir `http://localhost` en la barra de direcciones del explorador y comprobar si se muestra la página predeterminada de IIS. En algunos casos, los problemas también pueden deberse a un registro incorrecto de ASP.NET o WCF en IIS. Puede abrir el Símbolo del sistema para desarrolladores para Visual Studio y ejecutar el comando `aspnet_regiis.exe -ir` para corregir los problemas de registro de ASP.net o ejecutar el comando `ServiceModelReg.exe –ia` para corregir los problemas de registro de WCF.

## <a name="files-generated-for-publishing"></a>Archivos generados para publicación
 Antes de que una biblioteca de servicios WCF pueda hospedarse en Web, la herramienta genera los siguientes archivos: archivos de ensamblado, archivo de Web.config y archivo. SVC. Todos los archivos se copian en la ubicación de destino. A continuación se publica el servicio.

### <a name="assembly-files"></a>Archivos de ensamblado
 Al publicar un servicio WCF mediante esta herramienta, el servicio se compila primero automáticamente y los archivos de ensamblado se generan en el proyecto de servicio después de la compilación.

### <a name="svc-file"></a>Archivo .SVC
 La operación de publicación genera un archivo *. SVC para cada servicio WCF, tanto si el archivo existe como si no, para garantizar la validez de la versión. Hay dos tipos diferentes de archivos SVC: uno para la biblioteca de servicios de WCF y la biblioteca de servicios de distribución, y otro para la biblioteca de servicio de flujo de trabajo de equipo de estado y secuencial. El \* archivo. SVC generado se copia en la carpeta raíz en la ubicación de destino.

### <a name="webconfig-file"></a>Archivo Web.config
 Cada vez que un proyecto de servicio se publica en una ubicación de destino concreta, se crea un archivo Web.config.

 El archivo de Web.config generado incluye secciones web que son útiles para el hospedaje web y el contenido de App.config de la biblioteca de servicios WCF con los siguientes cambios:

- Se excluye la dirección base.

- La configuración del elemento `<diagnostics>` se excluye para conservar la configuración de seguimiento de la plataforma de destino.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Publicación de servicios WCF con enlaces que no son HTTP en IIS
 Si usa IIS 7.0 o posterior, puede publicar servicios WCF con enlaces que no son HTTP en IIS. Necesita realizar algunas tareas de configuración previa. Para obtener más información, consulte los temas en [hospedaje en el servicio de activación de procesos de Windows](./feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Seguridad
 Para la publicación en el servidor IIS local se requieren privilegios de administrador, porque IIS debe ejecutarse con la cuenta Administrador. Si un usuario sin privilegios de administrador abre la publicación de servicio WCF, IIS no estará disponible como ubicación de destino. La publicación en el sistema de archivos o el sitio FTP funciona sin privilegios de administrador.

## <a name="see-also"></a>Vea también

- [Plantillas de Visual Studio para WCF](wcf-vs-templates.md)
- [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Cliente de prueba de WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
