---
title: Codificador de ByteStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0984d3989d6441c363730454ea65b0393c94b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="bytestream-encoder"></a><span data-ttu-id="65f36-102">Codificador de ByteStream</span><span class="sxs-lookup"><span data-stu-id="65f36-102">ByteStream Encoder</span></span>
<span data-ttu-id="65f36-103">Este ejemplo muestra cómo crear un objeto `ByteStreamHttpBinding`, <xref:System.ServiceModel.Channels.Binding> que ilustra la funcionalidad del codificador del flujo de bytes.</span><span class="sxs-lookup"><span data-stu-id="65f36-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="65f36-104">Explicación</span><span class="sxs-lookup"><span data-stu-id="65f36-104">Discussion</span></span>  
 <span data-ttu-id="65f36-105">En este ejemplo se muestra cómo crear un objeto <xref:System.ServiceModel.Channels.Binding> estándar mediante los elementos de enlace estándar <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="65f36-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="65f36-106">En este ejemplo se muestra cómo utilizar el codificador de flujo de bytes para cargar y descargar una imagen.</span><span class="sxs-lookup"><span data-stu-id="65f36-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="65f36-107">La característica de codificador de flujo de bytes solo admite el transporte HTTP y no admite características como la mensajería de confianza o la seguridad.</span><span class="sxs-lookup"><span data-stu-id="65f36-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="65f36-108">La única <xref:System.ServiceModel.Channels.MessageVersion> que se admite es la propiedad <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="65f36-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65f36-109">Si va a ejecutar este ejemplo en [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], asegúrese de que va a ejecutar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="65f36-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65f36-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="65f36-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="65f36-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="65f36-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65f36-112">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65f36-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65f36-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="65f36-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65f36-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="65f36-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="65f36-115">Abra el archivo ByteStreamHttpBinding.sln en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65f36-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="65f36-116">Inicie una nueva instancia del proyecto ByteStreamHttpBindingServer haciendo clic en el proyecto en el Explorador de soluciones y seleccionando **depurar**y, a continuación, **Iniciar nueva instancia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="65f36-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="65f36-117">Inicie una nueva instancia del proyecto ByteStreamHttpBindingClient haciendo clic en el proyecto en el Explorador de soluciones y seleccionando **depurar**, **Iniciar nueva instancia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="65f36-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
