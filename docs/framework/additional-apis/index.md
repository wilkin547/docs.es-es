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
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053241"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="6702f-102">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="6702f-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="6702f-103">El .NET Framework evoluciona constantemente.</span><span class="sxs-lookup"><span data-stu-id="6702f-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="6702f-104">Para mejorar el desarrollo multiplataforma e introducir nuevas funciones con antelación, se lanzan nuevas características fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="6702f-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="6702f-105">En este tema se muestran los proyectos OOB para los que ofrecemos documentación.</span><span class="sxs-lookup"><span data-stu-id="6702f-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="6702f-106">Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6702f-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="6702f-107">Por ejemplo, la <xref:System.Text.CodePagesEncodingProvider> clase hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6702f-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="6702f-108">En este tema también se enumeran estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="6702f-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="6702f-109">Proyectos OOB</span><span class="sxs-lookup"><span data-stu-id="6702f-109">OOB projects</span></span>
  
| <span data-ttu-id="6702f-110">Proyecto</span><span class="sxs-lookup"><span data-stu-id="6702f-110">Project</span></span> | <span data-ttu-id="6702f-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6702f-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="6702f-112">Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido.</span><span class="sxs-lookup"><span data-stu-id="6702f-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="6702f-113">Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="6702f-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="6702f-114">Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.</span><span class="sxs-lookup"><span data-stu-id="6702f-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="6702f-115">La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="6702f-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="6702f-116">Bibliotecas específicas de plataforma</span><span class="sxs-lookup"><span data-stu-id="6702f-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="6702f-117">Proyecto</span><span class="sxs-lookup"><span data-stu-id="6702f-117">Project</span></span> | <span data-ttu-id="6702f-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6702f-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="6702f-119">Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de páginas de códigos estén disponibles para las aplicaciones destinadas a la plataforma universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="6702f-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="6702f-120">API privadas</span><span class="sxs-lookup"><span data-stu-id="6702f-120">Private APIs</span></span>  

<span data-ttu-id="6702f-121">Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="6702f-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="6702f-122">Nombre de API</span><span class="sxs-lookup"><span data-stu-id="6702f-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="6702f-123">System .net. Connection (clase)</span><span class="sxs-lookup"><span data-stu-id="6702f-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="6702f-124">Campo WriteList de System .net.\_Connection. m</span><span class="sxs-lookup"><span data-stu-id="6702f-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="6702f-125">System .net. ConnectionGroup (clase)</span><span class="sxs-lookup"><span data-stu-id="6702f-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="6702f-126">Campo ConnectionList de System .net.\_ConnectionGroup. m</span><span class="sxs-lookup"><span data-stu-id="6702f-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="6702f-127">System .net. CoreResponseData (clase)</span><span class="sxs-lookup"><span data-stu-id="6702f-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="6702f-128">Campo ResponseHeaders de System .net.\_CoreResponseData. m</span><span class="sxs-lookup"><span data-stu-id="6702f-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="6702f-129">Campo StatusCode de System .net.\_CoreResponseData. m</span><span class="sxs-lookup"><span data-stu-id="6702f-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="6702f-130">System .net. HttpWebRequest. \_Campo AutoRedirects</span><span class="sxs-lookup"><span data-stu-id="6702f-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="6702f-131">System .net. HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="6702f-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="6702f-132">System .net. HttpWebRequest. \_HttpResponse (campo)</span><span class="sxs-lookup"><span data-stu-id="6702f-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="6702f-133">Campo ConnectionGroupList de System .net.\_ServicePoint. m</span><span class="sxs-lookup"><span data-stu-id="6702f-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="6702f-134">Campo ServicePointTable de System .net.\_ServicePointManager. s</span><span class="sxs-lookup"><span data-stu-id="6702f-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="6702f-135">Campo isDebuggerCheckDisabledForTestPurposes de System. Windows. Diagnostics\_. VisualDiagnostics. s</span><span class="sxs-lookup"><span data-stu-id="6702f-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="6702f-136">Clase System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="6702f-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="6702f-137">Clase System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="6702f-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="6702f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6702f-138">See also</span></span>

- [<span data-ttu-id="6702f-139">.NET Framework y versiones fuera de banda</span><span class="sxs-lookup"><span data-stu-id="6702f-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
