---
title: Bibliotecas de clases y API adicionales
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3bb7a7c53cbca8bbd4026b46ce59589cef22382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="additional-class-libraries-and-apis"></a>Bibliotecas de clases y API adicionales

.NET Framework está evolucionando constantemente y para mejorar el desarrollo multiplataforma o para incluir una nueva funcionalidad, publicamos nuevas características fuera de banda (OOB). En este tema se muestran los proyectos OOB para los que ofrecemos documentación.  
  
Además, algunas bibliotecas se orientan a plataformas o implementaciones específicas de .NET Framework. Por ejemplo, el <xref:System.Text.CodePagesEncodingProvider> clase efectúa codificaciones de páginas de código disponibles para las aplicaciones UWP desarrolladas con .NET Framework. En este tema también se enumeran estas bibliotecas.  
  
## <a name="oob-projects"></a>Proyectos OOB
  
| Proyecto | Descripción |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Ofrece colecciones que son seguras para subprocesos en las que se garantiza que no cambiará nunca su contenido. |
| <xref:System.Net.Http.WinHttpHandler> | Ofrece un controlador de mensajes para <xref:System.Net.Http.HttpClient> basados en la interfaz de WinHTTP de Windows. |
| [System.Numerics.Vectors](https://msdn.microsoft.com/library/mt452176.aspx) | Ofrece una biblioteca de tipos de vector que puede beneficiarse de la aceleración basada en hardware de SIMD.| 
| <xref:System.Threading.Tasks.Dataflow> | La biblioteca de flujos de datos TPL ofrece componentes de flujo de datos que ayudan a aumentar la solidez de las aplicaciones habilitadas para simultaneidad. |  

## <a name="platform-specific-libraries"></a>Bibliotecas específicas de plataforma
  
| Proyecto | Descripción |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Extiende la <xref:System.Text.EncodingProvider> clase a disposición codificaciones de páginas de código a las aplicaciones que tienen como destino la plataforma Universal de Windows. |  
  
## <a name="private-apis"></a>API privadas  

Estas API admiten la infraestructura del producto y no están previstas ni se admiten para usarlas directamente en el código.  
  
| Nombre de API |
| -------- |
| [Clase System.Net.Connection](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList campo](../../../docs/framework/additional-apis/m_writelist.md) |
| [Clase System.Net.ConnectionGroup](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList campo](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.Net.HttpWebRequest. \_Campo HttpResponse](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.Net.HttpWebRequest. \_AutoRedirects campo](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList campo](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable campo](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes campo](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [Clase System.Windows.Forms.Design.DataMemberFieldEditor](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [Clase System.Windows.Forms.Design.DataMemberListEditor](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Vea también

[.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
