---
title: Enlace de datos en un cliente de Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b78cfbd63687fc7288c945ebcbec790150efed61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a><span data-ttu-id="d45d1-102">Enlace de datos en un cliente de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d45d1-102">Data Binding in a Windows Forms Client</span></span>
<span data-ttu-id="d45d1-103">Este ejemplo muestra cómo enlazar los datos devueltos por un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d45d1-103">This sample demonstrates how to bind to data returned by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Windows Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d45d1-104">El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="d45d1-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>  
  
 <span data-ttu-id="d45d1-105">Este ejemplo muestra un servicio que implementa un contrato que define un patrón de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="d45d1-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="d45d1-106">Este ejemplo se compone de una aplicación Windows Forms de cliente (.exe) y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alojado en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d45d1-106">The sample consists of a client Windows Forms application (.exe) and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="d45d1-107">El contrato se define mediante la interfaz `IWeatherService`, que expone una operación denominada `GetWeatherData`.</span><span class="sxs-lookup"><span data-stu-id="d45d1-107">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="d45d1-108">Esta operación acepta una matriz de ciudades y devuelve una matriz de objetos `WeatherData` que representan la temperatura alta y baja prevista para una ciudad.</span><span class="sxs-lookup"><span data-stu-id="d45d1-108">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="d45d1-109">El enlace de datos se produce en el cliente de la aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d45d1-109">The data binding occurs on the client in the Windows Forms application.</span></span> <span data-ttu-id="d45d1-110">Un `DataGridView`, se define en el Diseñador de Windows Forms, que es una representación gráfica de los datos. </span><span class="sxs-lookup"><span data-stu-id="d45d1-110">A `DataGridView` is defined in the Windows Forms designer, which is a graphical representation of the data.</span></span> <span data-ttu-id="d45d1-111">También se crea un objeto `BindingSource` con nombre intermedio.</span><span class="sxs-lookup"><span data-stu-id="d45d1-111">An intermediary named `BindingSource` is also created.</span></span> <span data-ttu-id="d45d1-112">El origen de datos de `BindingSource` se establece en la matriz de datos que devuelve el servicio.</span><span class="sxs-lookup"><span data-stu-id="d45d1-112">The data source of `BindingSource` is set to the data array returned by the service.</span></span> <span data-ttu-id="d45d1-113">La finalidad de `BindingSource` es proporcionar una capa de direccionamiento indirecto entre los datos y la vista de datos.</span><span class="sxs-lookup"><span data-stu-id="d45d1-113">The purpose of the `BindingSource` is to provide a layer of indirection between the data and the data view.</span></span> <span data-ttu-id="d45d1-114">Toda interacción con los datos, como navegación, ordenación, filtrado y actualización, se lleva a cabo mediante llamadas al componente `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="d45d1-114">All interaction with the data, such as navigating, sorting, filtering, and updating, is accomplished with calls to the `BindingSource` component.</span></span> <span data-ttu-id="d45d1-115">Para lograr el enlace de datos `DataGridView`, el `datasource` del `DataGridView` está establecido en el objeto `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="d45d1-115">To accomplish data binding to the `DataGridView`, the `datasource` of the `DataGridView` is then set to the `BindingSource` object.</span></span> <span data-ttu-id="d45d1-116">Después se muestran gráficamente todos los datos devueltos del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al usuario.</span><span class="sxs-lookup"><span data-stu-id="d45d1-116">All of the data returned from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is then displayed graphically to the user.</span></span>  <span data-ttu-id="d45d1-117">Cada vez que el usuario hace clic en el botón, se actualizan los datos devueltos automáticamente en el objeto `DataGridView` enlazado a datos.</span><span class="sxs-lookup"><span data-stu-id="d45d1-117">Every time the user clicks the button, the returned data is automatically updated in the data-bound `DataGridView`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d45d1-118">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d45d1-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d45d1-119">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d45d1-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d45d1-120">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d45d1-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d45d1-121">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d45d1-121">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d45d1-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d45d1-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d45d1-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d45d1-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d45d1-124">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d45d1-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d45d1-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d45d1-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a><span data-ttu-id="d45d1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d45d1-126">See Also</span></span>
