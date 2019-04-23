---
title: Orden de serialización personalizada con XmlSerializer
ms.date: 03/30/2017
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
ms.openlocfilehash: f63d460163c33c4253cf565a5755babc1030164f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295044"
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="5391d-102">Orden de serialización personalizada con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="5391d-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="5391d-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="5391d-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="5391d-104">En este ejemplo se muestra cómo controlar el orden de elementos serializados y deserializados para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="5391d-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="5391d-105">Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.</span><span class="sxs-lookup"><span data-stu-id="5391d-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="5391d-106">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="5391d-106">To build the sample using the Command Prompt</span></span>  
  
1. <span data-ttu-id="5391d-107">Abra la ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5391d-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="5391d-108">Escriba **msbuild CustomOrder.sln** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5391d-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="5391d-109">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5391d-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="5391d-110">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5391d-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="5391d-111">Haga doble clic en el icono CustomOrder.sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5391d-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="5391d-112">En el menú **Compilar**, seleccione **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="5391d-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4. <span data-ttu-id="5391d-113">La aplicación de ejemplo se generará en el subdirectorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="5391d-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5391d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5391d-114">See also</span></span>

- [<span data-ttu-id="5391d-115">Serialización básica</span><span class="sxs-lookup"><span data-stu-id="5391d-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="5391d-116">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="5391d-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="5391d-117">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="5391d-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="5391d-118">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="5391d-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="5391d-119">Serialización</span><span class="sxs-lookup"><span data-stu-id="5391d-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="5391d-120">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="5391d-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
