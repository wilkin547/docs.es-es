---
title: Bibliotecas de clases y API adicionales
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155913"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="909ee-102">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="909ee-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="909ee-103">.NET Framework está en constante evolución.</span><span class="sxs-lookup"><span data-stu-id="909ee-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="909ee-104">Para mejorar el desarrollo multiplataforma e introducir nuevas funciones de forma temprana, se lanzan nuevas características fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="909ee-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="909ee-105">En este tema se muestran los proyectos OOB para los que ofrecemos documentación.</span><span class="sxs-lookup"><span data-stu-id="909ee-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="909ee-106">Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="909ee-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="909ee-107">Por ejemplo, <xref:System.Text.CodePagesEncodingProvider> la clase hace que las codificaciones de página de códigos estén disponibles para las aplicaciones para UWP desarrolladas con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="909ee-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="909ee-108">En este tema también se enumeran estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="909ee-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="909ee-109">Proyectos OOB</span><span class="sxs-lookup"><span data-stu-id="909ee-109">OOB projects</span></span>
  
| <span data-ttu-id="909ee-110">proyecto</span><span class="sxs-lookup"><span data-stu-id="909ee-110">Project</span></span> | <span data-ttu-id="909ee-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="909ee-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="909ee-112">Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido.</span><span class="sxs-lookup"><span data-stu-id="909ee-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="909ee-113">Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="909ee-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="909ee-114">Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.</span><span class="sxs-lookup"><span data-stu-id="909ee-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="909ee-115">La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="909ee-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="909ee-116">Bibliotecas específicas de plataforma</span><span class="sxs-lookup"><span data-stu-id="909ee-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="909ee-117">proyecto</span><span class="sxs-lookup"><span data-stu-id="909ee-117">Project</span></span> | <span data-ttu-id="909ee-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="909ee-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="909ee-119">Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de página de códigos estén disponibles para las aplicaciones destinadas a la Plataforma universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="909ee-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="909ee-120">API privadas</span><span class="sxs-lookup"><span data-stu-id="909ee-120">Private APIs</span></span>  

<span data-ttu-id="909ee-121">Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="909ee-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="909ee-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item (Propiedad)</span><span class="sxs-lookup"><span data-stu-id="909ee-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="909ee-123">Método System.Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="909ee-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="909ee-124">Propiedad System.Data.SqlTypes.SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="909ee-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="909ee-125">System.Data.SqlTypes.SqlStreamChars Constructor</span><span class="sxs-lookup"><span data-stu-id="909ee-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="909ee-126">Propiedad System.Data.SqlTypes.SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="909ee-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="909ee-127">Propiedad System.Data.SqlTypes.SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="909ee-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="909ee-128">Propiedad System.Data.SqlTypes.SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="909ee-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="909ee-129">Método System.Data.SqlTypes.SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="909ee-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="909ee-130">Método System.Data.SqlTypes.SqlStreamChars.Dispose</span><span class="sxs-lookup"><span data-stu-id="909ee-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="909ee-131">Método System.Data.SqlTypes.SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="909ee-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="909ee-132">Método System.Data.SqlTypes.SqlStreamChars.Read</span><span class="sxs-lookup"><span data-stu-id="909ee-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="909ee-133">Método System.Data.SqlTypes.SqlStreamChars.Seek</span><span class="sxs-lookup"><span data-stu-id="909ee-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="909ee-134">Método System.Data.SqlTypes.SqlStreamChars.SetLength</span><span class="sxs-lookup"><span data-stu-id="909ee-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="909ee-135">Método System.Data.SqlTypes.SqlStreamChars.Write</span><span class="sxs-lookup"><span data-stu-id="909ee-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="909ee-136">Método System.IO.MemoryStream.InternalGetOriginAndLength</span><span class="sxs-lookup"><span data-stu-id="909ee-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="909ee-137">Clase System.Net.Connection</span><span class="sxs-lookup"><span data-stu-id="909ee-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="909ee-138">Campo WriteList System.Net.Connection.m\_</span><span class="sxs-lookup"><span data-stu-id="909ee-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="909ee-139">Clase System.Net.ConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="909ee-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="909ee-140">Campo ConnectionList System.Net.ConnectionGroup.m\_</span><span class="sxs-lookup"><span data-stu-id="909ee-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="909ee-141">Propiedad System.Net.ConnectStream.Connection</span><span class="sxs-lookup"><span data-stu-id="909ee-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="909ee-142">Clase System.Net.CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="909ee-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="909ee-143">Campo ResponseHeaders System.Net.CoreResponseData.m\_</span><span class="sxs-lookup"><span data-stu-id="909ee-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="909ee-144">Campo StatusCode System.Net.CoreResponseData.m\_</span><span class="sxs-lookup"><span data-stu-id="909ee-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="909ee-145">System.Net.HttpWebRequest. \_Campo de autoredirecciones</span><span class="sxs-lookup"><span data-stu-id="909ee-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="909ee-146">System.Net.HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="909ee-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="909ee-147">System.Net.HttpWebRequest. \_Campo HttpResponse</span><span class="sxs-lookup"><span data-stu-id="909ee-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="909ee-148">Propiedad System.Net.PooledStream.NetworkStream</span><span class="sxs-lookup"><span data-stu-id="909ee-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="909ee-149">Clase System.Net.RtcState</span><span class="sxs-lookup"><span data-stu-id="909ee-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="909ee-150">Campo ConnectionGroupList de\_System.Net.ServicePoint.m</span><span class="sxs-lookup"><span data-stu-id="909ee-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="909ee-151">Campo ServicePointTable System.Net.ServicePointManager.s\_</span><span class="sxs-lookup"><span data-stu-id="909ee-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="909ee-152">Campo System.Net.TlsStream.m_Worker</span><span class="sxs-lookup"><span data-stu-id="909ee-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="909ee-153">Propiedad System.Net.Security.SslState.SslProtocol</span><span class="sxs-lookup"><span data-stu-id="909ee-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="909ee-154">Método System.ServiceModel.Channels.Message.BodyToString</span><span class="sxs-lookup"><span data-stu-id="909ee-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="909ee-155">Método System.ServiceModel.Channels.Message.WriteStartHeaders</span><span class="sxs-lookup"><span data-stu-id="909ee-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="909ee-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="909ee-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="909ee-157">System.Windows.Forms.Design.DataMemberFieldEditor (Clase)</span><span class="sxs-lookup"><span data-stu-id="909ee-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="909ee-158">System.Windows.Forms.Design.DataMemberListEditor (Clase)</span><span class="sxs-lookup"><span data-stu-id="909ee-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="909ee-159">Método System.Xml.XmlReader.CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="909ee-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="909ee-160">Adodb. Interfaz de conexión</span><span class="sxs-lookup"><span data-stu-id="909ee-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="909ee-161">Adodb. EventReason Enum</span><span class="sxs-lookup"><span data-stu-id="909ee-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="909ee-162">Adodb. EventStatus Enum</span><span class="sxs-lookup"><span data-stu-id="909ee-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="909ee-163">stdole. Estructura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="909ee-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="909ee-164">stdole. Estructura EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="909ee-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="909ee-165">stdole. IFont.Name propiedad</span><span class="sxs-lookup"><span data-stu-id="909ee-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="909ee-166">stdole. Interfaz IFontDisp</span><span class="sxs-lookup"><span data-stu-id="909ee-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="909ee-167">stdole. Propiedad IPicture.Handle</span><span class="sxs-lookup"><span data-stu-id="909ee-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="909ee-168">stdole. Propiedad IPictureDisp.Handle</span><span class="sxs-lookup"><span data-stu-id="909ee-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="909ee-169">stdole. Interfaz StdFont</span><span class="sxs-lookup"><span data-stu-id="909ee-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="909ee-170">stdole. Interfaz StdPicture</span><span class="sxs-lookup"><span data-stu-id="909ee-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="909ee-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="909ee-171">See also</span></span>

* [<span data-ttu-id="909ee-172">.NET Framework y versiones fuera de banda</span><span class="sxs-lookup"><span data-stu-id="909ee-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
