---
title: Bibliotecas de clases y API adicionales
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 049268c29946e95ca7bb194f6cae38baf8f060f6
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079836"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="7ced2-102">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="7ced2-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="7ced2-103">.NET Framework evoluciona constantemente.</span><span class="sxs-lookup"><span data-stu-id="7ced2-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="7ced2-104">Para mejorar el desarrollo multiplataforma e introducir nuevas funciones al principio, se lanzan nuevas características fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="7ced2-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="7ced2-105">En este tema se muestran los proyectos OOB para los que ofrecemos documentación.</span><span class="sxs-lookup"><span data-stu-id="7ced2-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="7ced2-106">Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ced2-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="7ced2-107">Por ejemplo, el <xref:System.Text.CodePagesEncodingProvider> clase hace codificaciones de páginas de código disponibles para las aplicaciones para UWP desarrolladas con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ced2-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="7ced2-108">En este tema también se enumeran estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="7ced2-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="7ced2-109">Proyectos OOB</span><span class="sxs-lookup"><span data-stu-id="7ced2-109">OOB projects</span></span>
  
| <span data-ttu-id="7ced2-110">Proyecto</span><span class="sxs-lookup"><span data-stu-id="7ced2-110">Project</span></span> | <span data-ttu-id="7ced2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ced2-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="7ced2-112">Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido.</span><span class="sxs-lookup"><span data-stu-id="7ced2-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="7ced2-113">Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="7ced2-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="7ced2-114">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="7ced2-114">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="7ced2-115">Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.</span><span class="sxs-lookup"><span data-stu-id="7ced2-115">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="7ced2-116">La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="7ced2-116">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="7ced2-117">Bibliotecas específicas de plataforma</span><span class="sxs-lookup"><span data-stu-id="7ced2-117">Platform-specific libraries</span></span>
  
| <span data-ttu-id="7ced2-118">Proyecto</span><span class="sxs-lookup"><span data-stu-id="7ced2-118">Project</span></span> | <span data-ttu-id="7ced2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ced2-119">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="7ced2-120">Extiende la <xref:System.Text.EncodingProvider> clase a disposición codificaciones de páginas de código a las aplicaciones que tienen como destino la plataforma Universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="7ced2-120">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="7ced2-121">API privadas</span><span class="sxs-lookup"><span data-stu-id="7ced2-121">Private APIs</span></span>  

<span data-ttu-id="7ced2-122">Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="7ced2-122">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="7ced2-123">Nombre de API</span><span class="sxs-lookup"><span data-stu-id="7ced2-123">API Name</span></span> |
| -------- |
| [<span data-ttu-id="7ced2-124">Clase System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="7ced2-124">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="7ced2-125">System.Net.Connection.m\_WriteList campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-125">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="7ced2-126">Clase System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="7ced2-126">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="7ced2-127">System.Net.ConnectionGroup.m\_ConnectionList campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="7ced2-128">Clase System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="7ced2-128">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="7ced2-129">System.Net.CoreResponseData.m\_ResponseHeaders campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="7ced2-130">System.Net.CoreResponseData.m\_campo StatusCode</span><span class="sxs-lookup"><span data-stu-id="7ced2-130">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="7ced2-131">System.Net.HttpWebRequest. \_AutoRedirects campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-131">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="7ced2-132">System.Net.HttpWebRequest. \_CoreResponse campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-132">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="7ced2-133">System.Net.HttpWebRequest. \_HttpResponse campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-133">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="7ced2-134">System.Net.ServicePoint.m\_ConnectionGroupList campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-134">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="7ced2-135">System.Net.ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-135">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="7ced2-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes campo</span><span class="sxs-lookup"><span data-stu-id="7ced2-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="7ced2-137">Clase System.Windows.Forms.Design.DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="7ced2-137">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="7ced2-138">Clase System.Windows.Forms.Design.DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="7ced2-138">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="7ced2-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ced2-139">See also</span></span>

[<span data-ttu-id="7ced2-140">.NET Framework y versiones fuera de banda</span><span class="sxs-lookup"><span data-stu-id="7ced2-140">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
