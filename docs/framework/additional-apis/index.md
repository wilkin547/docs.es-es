---
title: Bibliotecas de clases y API adicionales
ms.custom: 
ms.date: 01/29/2018
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9ceb1ad24d4ba87fab7713ba61fed91eef26c4d
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="1ce92-102">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="1ce92-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="1ce92-103">.NET Framework está evolucionando constantemente y para mejorar el desarrollo multiplataforma o para incluir una nueva funcionalidad, publicamos nuevas características fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="1ce92-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="1ce92-104">En este tema se muestran los proyectos OOB para los que ofrecemos documentación.</span><span class="sxs-lookup"><span data-stu-id="1ce92-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="1ce92-105">Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ce92-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="1ce92-106">Por ejemplo, el <xref:System.Text.CodePagesEncodingProvider> clase efectúa codificaciones de páginas de código disponibles para las aplicaciones UWP desarrolladas con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ce92-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="1ce92-107">En este tema también se enumeran estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="1ce92-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="1ce92-108">Proyectos OOB</span><span class="sxs-lookup"><span data-stu-id="1ce92-108">OOB projects</span></span>
  
| <span data-ttu-id="1ce92-109">Proyecto</span><span class="sxs-lookup"><span data-stu-id="1ce92-109">Project</span></span> | <span data-ttu-id="1ce92-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ce92-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="1ce92-111">Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido.</span><span class="sxs-lookup"><span data-stu-id="1ce92-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="1ce92-112">Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ce92-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="1ce92-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="1ce92-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="1ce92-114">Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.</span><span class="sxs-lookup"><span data-stu-id="1ce92-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="1ce92-115">La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="1ce92-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="1ce92-116">Bibliotecas específicas de plataforma</span><span class="sxs-lookup"><span data-stu-id="1ce92-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="1ce92-117">Proyecto</span><span class="sxs-lookup"><span data-stu-id="1ce92-117">Project</span></span> | <span data-ttu-id="1ce92-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ce92-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="1ce92-119">Extiende la <xref:System.Text.EncodingProvider> clase a disposición codificaciones de páginas de código a las aplicaciones que tienen como destino la plataforma Universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ce92-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="1ce92-120">API privadas</span><span class="sxs-lookup"><span data-stu-id="1ce92-120">Private APIs</span></span>  

<span data-ttu-id="1ce92-121">Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="1ce92-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="1ce92-122">Nombre de API</span><span class="sxs-lookup"><span data-stu-id="1ce92-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="1ce92-123">Clase System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="1ce92-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="1ce92-124">System.Net.Connection.m\_WriteList Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="1ce92-125">Clase System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="1ce92-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="1ce92-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="1ce92-127">System.Net.CoreResponseData Class</span><span class="sxs-lookup"><span data-stu-id="1ce92-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="1ce92-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="1ce92-129">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="1ce92-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="1ce92-131">System.Net.HttpWebRequest.\_CoreResponse Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="1ce92-132">System.Net.HttpWebRequest.\_HttpResponse Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="1ce92-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="1ce92-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="1ce92-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="1ce92-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="1ce92-136">Clase System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="1ce92-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="1ce92-137">Clase System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="1ce92-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="1ce92-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ce92-138">See also</span></span>

[<span data-ttu-id="1ce92-139">.NET Framework y versiones fuera de banda</span><span class="sxs-lookup"><span data-stu-id="1ce92-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
