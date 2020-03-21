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
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

.NET Framework está en constante evolución. Para mejorar el desarrollo multiplataforma e introducir nuevas funciones de forma temprana, se lanzan nuevas características fuera de banda (OOB). En este tema se muestran los proyectos OOB para los que ofrecemos documentación.  
  
Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework. Por ejemplo, <xref:System.Text.CodePagesEncodingProvider> la clase hace que las codificaciones de página de códigos estén disponibles para las aplicaciones para UWP desarrolladas con .NET Framework. En este tema también se enumeran estas bibliotecas.  
  
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
| <xref:System.Text.CodePagesEncodingProvider> | Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de página de códigos estén disponibles para las aplicaciones destinadas a la Plataforma universal de Windows. |  
  
## <a name="private-apis"></a>API privadas  

Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.  
  
* [Microsoft.SqlServer.Server.SmiOrderProperty.Item (Propiedad)](microsoft.sqlserver.server.smiorderproperty.item.md)
* [Método System.Exception.PrepForRemoting](system.exception.prepforremoting.md)
* [Propiedad System.Data.SqlTypes.SqlChars.Stream](system.data.sqltypes.sqlchars.stream.md)
* [System.Data.SqlTypes.SqlStreamChars Constructor](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Propiedad System.Data.SqlTypes.SqlStreamChars.CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Propiedad System.Data.SqlTypes.SqlStreamChars.IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Propiedad System.Data.SqlTypes.SqlStreamChars.Length](system.data.sqltypes.sqlstreamchars.length.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Close](system.data.sqltypes.sqlstreamchars.close.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Dispose](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Método System.Data.SqlTypes.SqlStreamChars.SetLength](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Método System.Data.SqlTypes.SqlStreamChars.Write](system.data.sqltypes.sqlstreamchars.write.md)
* [Método System.IO.MemoryStream.InternalGetOriginAndLength](system.io.memorystream.internalgetoriginandlength.md)
* [Clase System.Net.Connection](connection.md)
* [Campo WriteList System.Net.Connection.m\_](m_writelist.md)
* [Clase System.Net.ConnectionGroup](connectiongroup.md)
* [Campo ConnectionList System.Net.ConnectionGroup.m\_](m_connectionlist.md)
* [Propiedad System.Net.ConnectStream.Connection](system.net.connectstream.connection.md)
* [Clase System.Net.CoreResponseData](coreresponsedata.md)
* [Campo ResponseHeaders System.Net.CoreResponseData.m\_](coreresponsedata_m_responseheaders.md)
* [Campo StatusCode System.Net.CoreResponseData.m\_](coreresponsedata_m_statuscode.md)
* [System.Net.HttpWebRequest. \_Campo de autoredirecciones](_autoredirects.md)
* [System.Net.HttpWebRequest. \_Campo CoreResponse](httpwebrequest__coreresponse.md)
* [System.Net.HttpWebRequest. \_Campo HttpResponse](_httpresponse.md)
* [Propiedad System.Net.PooledStream.NetworkStream](system.net.pooledstream.networkstream.md)
* [Clase System.Net.RtcState](system.net.rtcstate.md)
* [Campo ConnectionGroupList de\_System.Net.ServicePoint.m](m_connectiongrouplist.md)
* [Campo ServicePointTable System.Net.ServicePointManager.s\_](s_servicepointtable.md)
* [Campo System.Net.TlsStream.m_Worker](system.net.tlsstream.m_worker.md)
* [Propiedad System.Net.Security.SslState.SslProtocol](system.net.security.sslstate.sslprotocol.md)
* [Método System.ServiceModel.Channels.Message.BodyToString](system.servicemodel.channels.message.bodytostring.md)
* [Método System.ServiceModel.Channels.Message.WriteStartHeaders](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System.Windows.Forms.Design.DataMemberFieldEditor (Clase)](datamemberfieldeditor-class.md)
* [System.Windows.Forms.Design.DataMemberListEditor (Clase)](datamemberlisteditor-class.md)
* [Método System.Xml.XmlReader.CreateSqlReader](system.xml.xmlreader.createsqlreader.md)
* [Adodb. Interfaz de conexión](adodb.connection.md)
* [Adodb. EventReason Enum](adodb.eventreasonenum.md)
* [Adodb. EventStatus Enum](adodb.eventstatusenum.md)
* [stdole. Estructura DISPPARAMS](stdole.dispparams.md)
* [stdole. Estructura EXCEPINFO](stdole.excepinfo.md)
* [stdole. IFont.Name propiedad](stdole.ifont.name.md)
* [stdole. Interfaz IFontDisp](stdole.ifontdisp.md)
* [stdole. Propiedad IPicture.Handle](stdole.ipicture.handle.md)
* [stdole. Propiedad IPictureDisp.Handle](stdole.ipicturedisp.handle.md)
* [stdole. Interfaz StdFont](stdole.stdfont.md)
* [stdole. Interfaz StdPicture](stdole.stdpicture.md)
  
## <a name="see-also"></a>Consulte también

* [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
