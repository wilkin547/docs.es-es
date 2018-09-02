---
title: Capacidad de programación del almacén de metadatos
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423290"
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="6e8f8-102">Capacidad de programación del almacén de metadatos</span><span class="sxs-lookup"><span data-stu-id="6e8f8-102">Metadata Store Programmability</span></span>
<span data-ttu-id="6e8f8-103">El almacén de metadatos es una característica de [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] que permite la asociación de metadatos arbitrarios, en forma de atributos de CLR, con tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="6e8f8-104">Esto permite un acoplamiento separado entre los componentes de tiempo de ejecución y sus homólogos en tiempo de diseño, así como la capacidad de cambiar los componentes en tiempo de diseño sin afectar al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="6e8f8-105">En este ejemplo se muestra cómo realizar una programación en el almacén de metadatos aplicando atributos a un tipo en tiempo de ejecución, sobre cuyo origen no tenemos control alguno.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="6e8f8-106">La terminología normalmente utilizada es que una aplicación de hospedaje registra los metadatos para un conjunto de tipos.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="6e8f8-107">En la salida, es posible que observe un atributo adicional inesperado, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="6e8f8-108">Este atributo se agrega al utilizar la API de metadatos y no tiene ningún impacto en la ejecución del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="6e8f8-109">En este ejemplo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="6e8f8-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6e8f8-110">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="6e8f8-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="6e8f8-111">Inyección de atributos utilizando la API del almacén de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="6e8f8-112">Uso de un mecanismo de devolución de llamada para diferir el registro de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6e8f8-113">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e8f8-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6e8f8-114">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución ProgrammingMetadataStore.sln.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6e8f8-115">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6e8f8-116">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e8f8-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6e8f8-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6e8f8-119">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e8f8-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6e8f8-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`