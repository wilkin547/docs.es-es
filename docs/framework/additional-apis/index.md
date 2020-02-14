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
ms.openlocfilehash: 3a5134aa4407598e223fd2c938bfaac02cf9178c
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215538"
---
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

El .NET Framework evoluciona constantemente. Para mejorar el desarrollo multiplataforma e introducir nuevas funciones con antelación, se lanzan nuevas características fuera de banda (OOB). En este tema se muestran los proyectos OOB para los que ofrecemos documentación.  
  
Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework. Por ejemplo, la clase <xref:System.Text.CodePagesEncodingProvider> hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante el .NET Framework. En este tema también se enumeran estas bibliotecas.  
  
## <a name="oob-projects"></a>Proyectos OOB
  
| proyecto | Descripción |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido. |
| <xref:System.Net.Http.WinHttpHandler> | Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows. |
| <xref:System.Numerics> | Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad. |  

## <a name="platform-specific-libraries"></a>Bibliotecas específicas de plataforma
  
| proyecto | Descripción |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Extiende la clase <xref:System.Text.EncodingProvider> para que las codificaciones de páginas de códigos estén disponibles para las aplicaciones destinadas a la Plataforma universal de Windows. |  
  
## <a name="private-apis"></a>API privadas  

Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.  
  
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
* [System .net. Connection (clase)](connection.md)
* [System .net. Connection. m\_campo WriteList](m_writelist.md)
* [System .net. ConnectionGroup (clase)](connectiongroup.md)
* [Campo System .net. ConnectionGroup. m\_ConnectionList](m_connectionlist.md)
* [Propiedad System .net. ConnectStream. Connection](system.net.connectstream.connection.md)
* [System .net. CoreResponseData (clase)](coreresponsedata.md)
* [Campo System .net. CoreResponseData. m\_ResponseHeaders](coreresponsedata_m_responseheaders.md)
* [System .net. CoreResponseData. m\_campo StatusCode](coreresponsedata_m_statuscode.md)
* [Campo System .net. HttpWebRequest.\_AutoRedirects](_autoredirects.md)
* [Campo System .net. HttpWebRequest.\_CoreResponse](httpwebrequest__coreresponse.md)
* [Campo System .net. HttpWebRequest.\_HttpResponse](_httpresponse.md)
* [Propiedad System .net. PooledStream. NetworkStream](system.net.pooledstream.networkstream.md)
* [System .net. RtcState (clase)](system.net.rtcstate.md)
* [System .net. ServicePoint. m\_campo ConnectionGroupList](m_connectiongrouplist.md)
* [System .net. ServicePointManager. s\_campo ServicePointTable](s_servicepointtable.md)
* [Campo System .net. TlsStream. m_Worker](system.net.tlsstream.m_worker.md)
* [Propiedad System .net. Security. SslState. SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [System. ServiceModel. Channels. Message. BodyToString (método)](system.servicemodel.channels.message.bodytostring.md)
* [System. ServiceModel. Channels. Message. WriteStartHeaders (método)](system.servicemodel.channels.message.writestartheaders.md)
* [System. Windows. Diagnostics. VisualDiagnostics. s\_campo isDebuggerCheckDisabledForTestPurposes](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Clase System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Clase System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [System. Xml. XmlReader. CreateSqlReader (método)](system.xml.xmlreader.createsqlreader.md)
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

* [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
