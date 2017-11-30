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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72c7e9e1cbf47dd54726a16ddeb58a193d62dc31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="84cc0-102">Ejemplo de tecnología de servicios Web IXmlSerializable</span><span class="sxs-lookup"><span data-stu-id="84cc0-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="84cc0-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="84cc0-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="84cc0-104">En este ejemplo se muestra cómo utilizar <xref:System.Xml.Serialization.IXmlSerializable> para controlar la serialización de tipos personalizados en servicios Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="84cc0-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="84cc0-105">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="84cc0-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="84cc0-106">Abra [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] y seleccione **Nuevo sitio web** en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="84cc0-107">En el panel izquierdo del cuadro de diálogo **Nuevo sitio web**, seleccione el lenguaje de programación deseado y, en el panel derecho, seleccione **Servicio Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="84cc0-108">Escriba **IXmlSerializable** como el nombre del nuevo servicio web.</span><span class="sxs-lookup"><span data-stu-id="84cc0-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="84cc0-109">En la ventana Explorador de soluciones, haga clic con el botón derecho en el icono de Service.asmx y seleccione **Eliminar**; repita este paso para el archivo Service.asmx codebehind.</span><span class="sxs-lookup"><span data-stu-id="84cc0-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="84cc0-110">Haga clic con el botón derecho en el directorio de proyecto y seleccione **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="84cc0-111">En el cuadro de diálogo, navegue hasta el subdirectorio Servicio del directorio del lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="84cc0-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="84cc0-112">Seleccione Service.asmx y, a continuación, repita este paso para el archivo Service.asmx codebehind.</span><span class="sxs-lookup"><span data-stu-id="84cc0-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="84cc0-113">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta el directorio que contiene el directorio IXmlSerializable que creó anteriormente en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="84cc0-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="84cc0-114">Haga clic con el botón derecho en el icono del directorio IXmlSerializable y seleccione **Compartir y seguridad**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="84cc0-115">En la pestaña Uso compartido de web, seleccione **Compartir esta carpeta** y confirme la configuración predeterminada, incluido el nombre IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="84cc0-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="84cc0-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="84cc0-117">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="84cc0-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="84cc0-118">Abra una ventana del explorador y seleccione su barra de direcciones.</span><span class="sxs-lookup"><span data-stu-id="84cc0-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="84cc0-119">Escriba **http://localhost/IXmlSerializable/Service.asmx**.</span><span class="sxs-lookup"><span data-stu-id="84cc0-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cc0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="84cc0-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
