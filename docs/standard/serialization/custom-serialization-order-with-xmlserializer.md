---
title: "Orden de serialización personalizada con XmlSerializer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae5969060938763fee63c514de0a87eadbe6537a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="ed156-102">Orden de serialización personalizada con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="ed156-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="ed156-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed156-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="ed156-104">En este ejemplo se muestra cómo controlar el orden de elementos serializados y deserializados para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="ed156-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="ed156-105">Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.</span><span class="sxs-lookup"><span data-stu-id="ed156-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="ed156-106">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="ed156-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="ed156-107">Abra la ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ed156-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="ed156-108">Escriba **msbuild CustomOrder.sln** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed156-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="ed156-109">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed156-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="ed156-110">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ed156-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="ed156-111">Haga doble clic en el icono CustomOrder.sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ed156-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="ed156-112">En el menú **Compilar**, seleccione **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="ed156-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="ed156-113">La aplicación de ejemplo se generará en el subdirectorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="ed156-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed156-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed156-114">See Also</span></span>  
 [<span data-ttu-id="ed156-115">Serialización básica</span><span class="sxs-lookup"><span data-stu-id="ed156-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="ed156-116">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="ed156-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="ed156-117">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="ed156-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="ed156-118">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="ed156-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="ed156-119">Serialización</span><span class="sxs-lookup"><span data-stu-id="ed156-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="ed156-120">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="ed156-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
