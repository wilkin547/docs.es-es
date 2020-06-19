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
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

En este artículo se enumeran .NET Framework API que se lanzaron fuera de banda, se destinan a una plataforma específica o son tipos privados o internos.

## <a name="oob-projects"></a>Proyectos OOB

Para mejorar el desarrollo multiplataforma e introducir una nueva funcionalidad al principio, algunas características de .NET Framework se publicaron fuera de banda (OOB).

| Project | Descripción |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido. |
| <xref:System.Net.Http.WinHttpHandler> | Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows. |
| <xref:System.Numerics> | Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.|
| <xref:System.Threading.Tasks.Dataflow> | La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad. |  

## <a name="platform-specific-libraries"></a>Bibliotecas específicas de plataforma

Algunas bibliotecas tienen como destino plataformas específicas. Por ejemplo, la <xref:System.Text.CodePagesEncodingProvider> clase hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante .NET Framework.
  
| Project | Descripción |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de páginas de códigos estén disponibles para las aplicaciones destinadas a la plataforma universal de Windows. |  
  
## <a name="private-apis"></a>API privadas  

Estas API admiten la infraestructura del producto y no están pensadas ni se admiten para usarse directamente desde el código.  
  
* [Propiedad Microsoft. SqlServer. Server. SmiOrderProperty. Item](microsoft.sqlserver.server.smiorderproperty.item.md)
* [System. Exception. PrepForRemoting (método)](system.exception.prepforremoting.md)
* [Propiedad System. Data. SqlTypes. SqlChars. Stream](system.data.sqltypes.sqlchars.stream.md)
* [Constructor System. Data. SqlTypes. SqlStreamChars](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Propiedad System. Data. SqlTypes. SqlStreamChars. CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Propiedad System. Data. SqlTypes. SqlStreamChars. IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Propiedad System. Data. SqlTypes. SqlStreamChars. length](system.data.sqltypes.sqlstreamchars.length.md)
* [System. Data. SqlTypes. SqlStreamChars. Close (método)](system.data.sqltypes.sqlstreamchars.close.md)
* [System. Data. SqlTypes. SqlStreamChars. Dispose (método)](system.data.sqltypes.sqlstreamchars.dispose.md)
* [System. Data. SqlTypes. SqlStreamChars. Flush (método)](system.data.sqltypes.sqlstreamchars.flush.md)
* [System. Data. SqlTypes. SqlStreamChars. Read (método)](system.data.sqltypes.sqlstreamchars.read.md)
* [System. Data. SqlTypes. SqlStreamChars. Seek (método)](system.data.sqltypes.sqlstreamchars.seek.md)
* [System. Data. SqlTypes. SqlStreamChars. SetLength (método)](system.data.sqltypes.sqlstreamchars.setlength.md)
* [System. Data. SqlTypes. SqlStreamChars. Write (método)](system.data.sqltypes.sqlstreamchars.write.md)
* [System. IO. MemoryStream. InternalGetOriginAndLength (método)](system.io.memorystream.internalgetoriginandlength.md)
* [System .net. comnetos (clase)](system.net.comnetos.md)
* [System .net. Connection (clase)](connection.md)
* [Campo WriteList de System .net. Connection. m \_](m_writelist.md)
* [System .net. ConnectionGroup (clase)](connectiongroup.md)
* [Campo ConnectionList de System .net. ConnectionGroup. m \_](m_connectionlist.md)
* [Propiedad System .net. ConnectStream. Connection](system.net.connectstream.connection.md)
* [System .net. CoreResponseData (clase)](coreresponsedata.md)
* [Campo ResponseHeaders de System .net. CoreResponseData. m \_](coreresponsedata_m_responseheaders.md)
* [Campo StatusCode de System .net. CoreResponseData. m \_](coreresponsedata_m_statuscode.md)
* [System .net. ExceptionHelper (clase)](system.net.exceptionhelper.md)
* [System .net. HttpStatusDescription (clase)](system.net.httpstatusdescription.md)
* [System .net. HttpWebRequest. \_ Campo AutoRedirects](_autoredirects.md)
* [System .net. HttpWebRequest. \_ Campo CoreResponse](httpwebrequest__coreresponse.md)
* [System .net. HttpWebRequest. \_ HttpResponse (campo)](_httpresponse.md)
* [System .net. Logging (clase)](system.net.logging.md)
* [Clase System .net. mail. MailAddressParser](system.net.mail.mailaddressparser.md)
* [Clase System .net. mail. QuotedPairReader](system.net.mail.quotedpairreader.md)
* [System .net. MIME. MailBnfHelper (clase)](system.net.mime.mailbnfhelper.md)
* [Propiedad System .net. PooledStream. NetworkStream](system.net.pooledstream.networkstream.md)
* [System .net. RtcState (clase)](system.net.rtcstate.md)
* [Propiedad System .net. Security. SslState. SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [Campo ConnectionGroupList de System .net. ServicePoint. m \_](m_connectiongrouplist.md)
* [System .net. ServicePointManager. CloseConnectionGroups (método)](system.net.servicepointmanager.closeconnectiongroups.md)
* [Campo ServicePointTable de System .net. ServicePointManager. s \_](s_servicepointtable.md)
* [Campo System .net. TlsStream. m_Worker](system.net.tlsstream.m_worker.md)
* [System .net. UnsafeNclNativeMethods (clase)](system.net.unsafenclnativemethods.md)
* [System .net. WebHeaderCollection. AddInternal (método)](system.net.webheadercollection.addinternal.md)
* [System. ServiceModel. Channels. Message. BodyToString (método)](system.servicemodel.channels.message.bodytostring.md)
* [System. ServiceModel. Channels. Message. WriteStartHeaders (método)](system.servicemodel.channels.message.writestartheaders.md)
* [Campo isDebuggerCheckDisabledForTestPurposes de System. Windows. Diagnostics. VisualDiagnostics. s \_](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Clase System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Clase System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [System.Xml.Xmlmétodo Reader. CreateSqlReader](system.xml.xmlreader.createsqlreader.md)
* [ADODB. Interfaz de conexión](adodb.connection.md)
* [ADODB. Enumeración EventReason](adodb.eventreasonenum.md)
* [ADODB. Enumeración EventStatus](adodb.eventstatusenum.md)
* [dicha. Estructura DISPPARAMS](stdole.dispparams.md)
* [dicha. Estructura EXCEPINFO](stdole.excepinfo.md)
* [dicha. Propiedad IFont.Name](stdole.ifont.name.md)
* [dicha. IFontDisp (interfaz)](stdole.ifontdisp.md)
* [dicha. IPicture. Handle (propiedad)](stdole.ipicture.handle.md)
* [dicha. IPictureDisp. Handle (propiedad)](stdole.ipicturedisp.handle.md)
* [dicha. StdFont (interfaz)](stdole.stdfont.md)
* [dicha. StdPicture (interfaz)](stdole.stdpicture.md)
  
## <a name="see-also"></a>Consulte también

* [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
