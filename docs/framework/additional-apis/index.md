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
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

El .NET Framework evoluciona constantemente. Para mejorar el desarrollo multiplataforma e introducir nuevas funciones con antelación, se lanzan nuevas características fuera de banda (OOB). En este tema se muestran los proyectos OOB para los que ofrecemos documentación.  
  
Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework. Por ejemplo, la <xref:System.Text.CodePagesEncodingProvider> clase hace que las codificaciones de páginas de códigos estén disponibles para las aplicaciones UWP desarrolladas mediante el .NET Framework. En este tema también se enumeran estas bibliotecas.  
  
## <a name="oob-projects"></a>Proyectos OOB
  
| Proyecto | DESCRIPCIÓN |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido. |
| <xref:System.Net.Http.WinHttpHandler> | Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows. |
| <xref:System.Numerics> | Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad. |  

## <a name="platform-specific-libraries"></a>Bibliotecas específicas de plataforma
  
| Proyecto | DESCRIPCIÓN |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Extiende la <xref:System.Text.EncodingProvider> clase para que las codificaciones de páginas de códigos estén disponibles para las aplicaciones destinadas a la plataforma universal de Windows. |  
  
## <a name="private-apis"></a>API privadas  

Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.  
  
| Nombre de API |
| -------- |
| [System .net. Connection (clase)](connection.md) |
| [Campo WriteList de System .net.\_Connection. m](m_writelist.md) |
| [System .net. ConnectionGroup (clase)](connectiongroup.md) |
| [Campo ConnectionList de System .net.\_ConnectionGroup. m](m_connectionlist.md) |
| [System .net. CoreResponseData (clase)](coreresponsedata.md) |
| [Campo ResponseHeaders de System .net.\_CoreResponseData. m](coreresponsedata_m_responseheaders.md) |
| [Campo StatusCode de System .net.\_CoreResponseData. m](coreresponsedata_m_statuscode.md) |
| [System .net. HttpWebRequest. \_Campo AutoRedirects](_autoredirects.md) |
| [System .net. HttpWebRequest. \_Campo CoreResponse](httpwebrequest__coreresponse.md) |
| [System .net. HttpWebRequest. \_HttpResponse (campo)](_httpresponse.md) |
| [Campo ConnectionGroupList de System .net.\_ServicePoint. m](m_connectiongrouplist.md) |
| [Campo ServicePointTable de System .net.\_ServicePointManager. s](s_servicepointtable.md) |
| [Campo isDebuggerCheckDisabledForTestPurposes de System. Windows. Diagnostics\_. VisualDiagnostics. s](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [Clase System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md) |
| [Clase System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Vea también

- [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
