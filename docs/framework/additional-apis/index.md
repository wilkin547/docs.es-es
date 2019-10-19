---
title: Bibliotecas de clases y API adicionales
ms.date: 10/17/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 809ac026244b24aee69ec0d6c40c10a1248c234c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579114"
---
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

El .NET Framework evoluciona constantemente. Para mejorar el desarrollo multiplataforma e introducir nuevas funciones con antelación, se lanzan nuevas características fuera de banda (OOB). En este tema se muestran los proyectos OOB para los que ofrecemos documentación.  
  
Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework. Por ejemplo, la clase <xref:System.Text.CodePagesEncodingProvider> hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante el .NET Framework. En este tema también se enumeran estas bibliotecas.  
  
## <a name="oob-projects"></a>Proyectos OOB
  
| Proyecto | Descripción |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido. |
| <xref:System.Net.Http.WinHttpHandler> | Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows. |
| <xref:System.Numerics> | Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad. |  

## <a name="platform-specific-libraries"></a>Bibliotecas específicas de plataforma
  
| Proyecto | Descripción |  
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
* [System .net. Connection (clase)](connection.md)
* [Campo de \_WriteList System .net. Connection. m](m_writelist.md)
* [System .net. ConnectionGroup (clase)](connectiongroup.md)
* [Campo de \_ConnectionList System .net. ConnectionGroup. m](m_connectionlist.md)
* [System .net. CoreResponseData (clase)](coreresponsedata.md)
* [Campo de \_ResponseHeaders System .net. CoreResponseData. m](coreresponsedata_m_responseheaders.md)
* [Campo de \_StatusCode System .net. CoreResponseData. m](coreresponsedata_m_statuscode.md)
* [Campo System .net. HttpWebRequest. \_AutoRedirects](_autoredirects.md)
* [Campo System .net. HttpWebRequest. \_CoreResponse](httpwebrequest__coreresponse.md)
* [Campo System .net. HttpWebRequest. \_HttpResponse](_httpresponse.md)
* [Campo de \_ConnectionGroupList System .net. ServicePoint. m](m_connectiongrouplist.md)
* [Campo de \_ServicePointTable System .net. ServicePointManager. s](s_servicepointtable.md)
* [Campo de \_isDebuggerCheckDisabledForTestPurposes System. Windows. Diagnostics. VisualDiagnostics. s](s-isdebuggercheckdisabledfortestpurposes-field.md)
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
  
## <a name="see-also"></a>Vea también

* [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
