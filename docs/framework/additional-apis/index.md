---
title: Bibliotecas de clases y API adicionales
description: Explore bibliotecas de clases y API adicionales en .NET, incluidos proyectos fuera de banda (OOB), bibliotecas específicas de la plataforma y API privadas.
ms.date: 06/12/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 0b888d2f0e80685ba993682b2f3067cf8aee15bc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989733"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="e302e-103">Bibliotecas de clases y API adicionales</span><span class="sxs-lookup"><span data-stu-id="e302e-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="e302e-104">En este artículo se enumeran .NET Framework API que se lanzaron fuera de banda, se destinan a una plataforma específica o son tipos privados o internos.</span><span class="sxs-lookup"><span data-stu-id="e302e-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="e302e-105">Proyectos OOB</span><span class="sxs-lookup"><span data-stu-id="e302e-105">OOB projects</span></span>

<span data-ttu-id="e302e-106">Para mejorar el desarrollo multiplataforma e introducir una nueva funcionalidad al principio, algunas características de .NET Framework se publicaron fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="e302e-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="e302e-107">Project</span><span class="sxs-lookup"><span data-stu-id="e302e-107">Project</span></span> | <span data-ttu-id="e302e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e302e-108">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="e302e-109">Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido.</span><span class="sxs-lookup"><span data-stu-id="e302e-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="e302e-110">Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="e302e-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="e302e-111">Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.</span><span class="sxs-lookup"><span data-stu-id="e302e-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="e302e-112">La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="e302e-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="e302e-113">Bibliotecas específicas de plataforma</span><span class="sxs-lookup"><span data-stu-id="e302e-113">Platform-specific libraries</span></span>

<span data-ttu-id="e302e-114">Algunas bibliotecas tienen como destino plataformas específicas.</span><span class="sxs-lookup"><span data-stu-id="e302e-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="e302e-115">Por ejemplo, la <xref:System.Text.CodePagesEncodingProvider> clase hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e302e-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>
  
| <span data-ttu-id="e302e-116">Project</span><span class="sxs-lookup"><span data-stu-id="e302e-116">Project</span></span> | <span data-ttu-id="e302e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e302e-117">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="e302e-118">Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de páginas de códigos estén disponibles para las aplicaciones destinadas a la plataforma universal de Windows.</span><span class="sxs-lookup"><span data-stu-id="e302e-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="e302e-119">API privadas</span><span class="sxs-lookup"><span data-stu-id="e302e-119">Private APIs</span></span>  

<span data-ttu-id="e302e-120">Estas API admiten la infraestructura del producto y no están pensadas ni se admiten para usarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e302e-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="e302e-121">Propiedad Microsoft. SqlServer. Server. SmiOrderProperty. Item</span><span class="sxs-lookup"><span data-stu-id="e302e-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="e302e-122">System. Exception. PrepForRemoting (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="e302e-123">Propiedad System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="e302e-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="e302e-124">Constructor System. Data. SqlTypes. SqlStreamChars</span><span class="sxs-lookup"><span data-stu-id="e302e-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="e302e-125">Propiedad System. Data. SqlTypes. SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="e302e-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="e302e-126">Propiedad System. Data. SqlTypes. SqlStreamChars. IsNull</span><span class="sxs-lookup"><span data-stu-id="e302e-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="e302e-127">Propiedad System. Data. SqlTypes. SqlStreamChars. length</span><span class="sxs-lookup"><span data-stu-id="e302e-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="e302e-128">System. Data. SqlTypes. SqlStreamChars. Close (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="e302e-129">System. Data. SqlTypes. SqlStreamChars. Dispose (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="e302e-130">System. Data. SqlTypes. SqlStreamChars. Flush (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="e302e-131">System. Data. SqlTypes. SqlStreamChars. Read (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="e302e-132">System. Data. SqlTypes. SqlStreamChars. Seek (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="e302e-133">System. Data. SqlTypes. SqlStreamChars. SetLength (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="e302e-134">System. Data. SqlTypes. SqlStreamChars. Write (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="e302e-135">System. IO. MemoryStream. InternalGetOriginAndLength (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="e302e-136">System .net. comnetos (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="e302e-137">System .net. Connection (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="e302e-138">Campo WriteList de System .net. Connection. m \_</span><span class="sxs-lookup"><span data-stu-id="e302e-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="e302e-139">System .net. ConnectionGroup (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="e302e-140">Campo ConnectionList de System .net. ConnectionGroup. m \_</span><span class="sxs-lookup"><span data-stu-id="e302e-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="e302e-141">Propiedad System .net. ConnectStream. Connection</span><span class="sxs-lookup"><span data-stu-id="e302e-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="e302e-142">System .net. CoreResponseData (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="e302e-143">Campo ResponseHeaders de System .net. CoreResponseData. m \_</span><span class="sxs-lookup"><span data-stu-id="e302e-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="e302e-144">Campo StatusCode de System .net. CoreResponseData. m \_</span><span class="sxs-lookup"><span data-stu-id="e302e-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="e302e-145">System .net. ExceptionHelper (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="e302e-146">System .net. HttpStatusDescription (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="e302e-147">System .net. HttpWebRequest. \_ Campo AutoRedirects</span><span class="sxs-lookup"><span data-stu-id="e302e-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="e302e-148">System .net. HttpWebRequest. \_ Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="e302e-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="e302e-149">System .net. HttpWebRequest. \_ HttpResponse (campo)</span><span class="sxs-lookup"><span data-stu-id="e302e-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="e302e-150">System .net. Logging (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="e302e-151">Clase System .net. mail. MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="e302e-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="e302e-152">Clase System .net. mail. QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="e302e-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="e302e-153">System .net. MIME. MailBnfHelper (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="e302e-154">Propiedad System .net. PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="e302e-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="e302e-155">System .net. RtcState (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="e302e-156">Propiedad System .net. Security. SslState. SslProtocol</span><span class="sxs-lookup"><span data-stu-id="e302e-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="e302e-157">Campo ConnectionGroupList de System .net. ServicePoint. m \_</span><span class="sxs-lookup"><span data-stu-id="e302e-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="e302e-158">System .net. ServicePointManager. CloseConnectionGroups (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="e302e-159">Campo ServicePointTable de System .net. ServicePointManager. s \_</span><span class="sxs-lookup"><span data-stu-id="e302e-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="e302e-160">Campo System .net. TlsStream. m_Worker</span><span class="sxs-lookup"><span data-stu-id="e302e-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="e302e-161">System .net. UnsafeNclNativeMethods (clase)</span><span class="sxs-lookup"><span data-stu-id="e302e-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="e302e-162">System .net. WebHeaderCollection. AddInternal (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="e302e-163">System. ServiceModel. Channels. Message. BodyToString (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="e302e-164">System. ServiceModel. Channels. Message. WriteStartHeaders (método)</span><span class="sxs-lookup"><span data-stu-id="e302e-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="e302e-165">Campo isDebuggerCheckDisabledForTestPurposes de System. Windows. Diagnostics. VisualDiagnostics. s \_</span><span class="sxs-lookup"><span data-stu-id="e302e-165">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="e302e-166">Clase System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="e302e-166">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="e302e-167">Clase System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="e302e-167">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="e302e-168">System.Xml.Xmlmétodo Reader. CreateSqlReader</span><span class="sxs-lookup"><span data-stu-id="e302e-168">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="e302e-169">ADODB. Interfaz de conexión</span><span class="sxs-lookup"><span data-stu-id="e302e-169">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="e302e-170">ADODB. Enumeración EventReason</span><span class="sxs-lookup"><span data-stu-id="e302e-170">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="e302e-171">ADODB. Enumeración EventStatus</span><span class="sxs-lookup"><span data-stu-id="e302e-171">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="e302e-172">dicha. Estructura DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="e302e-172">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="e302e-173">dicha. Estructura EXCEPINFO</span><span class="sxs-lookup"><span data-stu-id="e302e-173">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="e302e-174">dicha. Propiedad IFont.Name</span><span class="sxs-lookup"><span data-stu-id="e302e-174">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="e302e-175">dicha. IFontDisp (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e302e-175">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="e302e-176">dicha. IPicture. Handle (propiedad)</span><span class="sxs-lookup"><span data-stu-id="e302e-176">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="e302e-177">dicha. IPictureDisp. Handle (propiedad)</span><span class="sxs-lookup"><span data-stu-id="e302e-177">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="e302e-178">dicha. StdFont (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e302e-178">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="e302e-179">dicha. StdPicture (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e302e-179">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="e302e-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e302e-180">See also</span></span>

* [<span data-ttu-id="e302e-181">.NET Framework y versiones fuera de banda</span><span class="sxs-lookup"><span data-stu-id="e302e-181">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
