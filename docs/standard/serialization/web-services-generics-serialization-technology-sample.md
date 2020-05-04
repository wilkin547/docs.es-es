---
title: Ejemplo de Web Services Generics Serialization Technology
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 467bfe1fd9eb8a0222385c34cb29a90df00dc937
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960748"
---
# <a name="web-services-generics-serialization-technology-sample"></a>Ejemplo de Web Services Generics Serialization Technology
[Descargar ejemplo](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 Este ejemplo muestra cómo utilizar y controlar la serialización de genéricos en servicios Web ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Para compilar el ejemplo con Visual Studio  
  
1. Abra Visual Studio y seleccione **Nuevo sitio web** en el menú **Archivo**.  
  
2. En el panel izquierdo del cuadro de diálogo **Nuevo sitio web**, seleccione su lenguaje de programación deseado y, a continuación, en el panel derecho, seleccione **Servicio Web ASP.NET**.  
  
3. Haga clic en **Examinar** y desplácese hasta el subdirectorio del \CS\GenericsService.  
  
4. Seleccione Service.asmx para abrir el archivo en Visual Studio.  
  
5. En el menú **Compilar** , haga clic en **Compilar solución**.  
  
> [!NOTE]
> Los primeros cinco pasos en esta lista son opcionales. El runtime de .NET Framework generará automáticamente el servicio Web la primera vez que se solicita el servicio.  
  
> [!NOTE]
> Los siguientes pasos son obligatorios para generar el ejemplo.  
  
1. Abra el Explorador de archivos y navegue hasta el subdirectorio \CS.  
  
2. Haga clic con el botón secundario en el icono del subdirectorio GenericsService y seleccione **Compartir y seguridad**.  
  
3. En la pestaña **Uso compartido de web**, seleccione **Compartir esta carpeta**.  
  
> [!IMPORTANT]
> Tome nota del nombre del directorio virtual que aparece en la lista en el panel **Alias**, porque necesitará para ejecutar el ejemplo.  
  
### <a name="to-build-the-sample-using-internet-information-services"></a>Para generar el ejemplo mediante Internet Information Services  
  
1. Abra el complemento de administración de **Internet Information Services** y expanda **Sitios web**.  
  
2. Haga clic en **Sitio web predeterminado** y seleccione **Nuevo**, **Directorio virtual** para crear el **Asistente para crear un directorio virtual**.  
  
3. Haga clic en **Siguiente**, escriba el alias público para su directorio virtual y haga clic en **Siguiente**.  
  
4. Escriba la ruta de acceso al directorio donde guardó el ejemplo (normalmente el subdirectorio del \CS\GenericsService) y haga clic en **Siguiente**. Haga clic en **Siguiente** para cerrar el asistente.  
  
> [!IMPORTANT]
> Tome nota del nombre del directorio virtual que aparece en la lista en el panel **Alias**, porque necesitará para ejecutar el ejemplo.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1. Abra una ventana del explorador y seleccione su barra de direcciones.  
  
2. Escriba `http://localhost/[virtual directory]/Service.asmx`, donde `[virtual directory]` representa el directorio virtual que ha creado al compilar el ejemplo.  
  
## <a name="remarks"></a>Comentarios  
 En el ejemplo se muestra una página ASP.NET predeterminada que contiene los vínculos a la definición del servicio Web. Puede personalizar la presentación además de modificar el código fuente del servicio Web. Para obtener más información, vea [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)) (Crear clientes de servicios Web XML).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [Serialización](../../../docs/standard/serialization/index.md)
- [Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
