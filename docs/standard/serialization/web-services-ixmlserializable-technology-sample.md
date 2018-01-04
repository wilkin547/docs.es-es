---
title: "Ejemplo de tecnología de servicios Web IXmlSerializable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: be0c76371bda9e91e0becf8a9e09beb44e44dd3c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a>Ejemplo de tecnología de servicios Web IXmlSerializable
[Descargar ejemplo](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 En este ejemplo se muestra cómo utilizar <xref:System.Xml.Serialization.IXmlSerializable> para controlar la serialización de tipos personalizados en servicios Web ASP.NET.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Para compilar el ejemplo con Visual Studio  
  
1.  Abra [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] y seleccione **Nuevo sitio web** en el menú **Archivo**.  
  
2.  En el panel izquierdo del cuadro de diálogo **Nuevo sitio web**, seleccione el lenguaje de programación deseado y, en el panel derecho, seleccione **Servicio Web ASP.NET**.  
  
3.  Escriba **IXmlSerializable** como el nombre del nuevo servicio web.  
  
4.  En la ventana Explorador de soluciones, haga clic con el botón derecho en el icono de Service.asmx y seleccione **Eliminar**; repita este paso para el archivo Service.asmx codebehind.  
  
5.  Haga clic con el botón derecho en el directorio de proyecto y seleccione **Agregar elemento existente**. En el cuadro de diálogo, navegue hasta el subdirectorio Servicio del directorio del lenguaje específico.  
  
6.  Seleccione Service.asmx y, a continuación, repita este paso para el archivo Service.asmx codebehind.  
  
7.  Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta el directorio que contiene el directorio IXmlSerializable que creó anteriormente en el paso 3.  
  
8.  Haga clic con el botón derecho en el icono del directorio IXmlSerializable y seleccione **Compartir y seguridad**.  
  
9. En la pestaña Uso compartido de web, seleccione **Compartir esta carpeta** y confirme la configuración predeterminada, incluido el nombre IXmlSerializable.  
  
10. Haga clic en **Aceptar**.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra una ventana del explorador y seleccione su barra de direcciones.  
  
2.  Escriba **http://localhost/IXmlSerializable/Service.asmx**.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
