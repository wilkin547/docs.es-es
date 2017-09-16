---
title: Interpretar el seguimiento de red
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e8c451a84117208457942d1c3794628963a49e93
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="interpreting-network-tracing"></a>Interpretar el seguimiento de red
Cuando está habilitado el seguimiento de red, puede usarlo para capturar las llamadas que la aplicación realiza a diversos miembros de clase <xref:System.Net>. La salida de estas llamadas puede ser similar a los ejemplos siguientes.  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 En el ejemplo anterior, [588] es el identificador único del subproceso actual. (4357) y (4387) son marcas de tiempo que indican el número de milisegundos que han transcurrido desde que se ha iniciado la aplicación. Los datos que aparecen después de la marca de tiempo muestran la aplicación que entra y sale del método **Socket.Send**. El objeto que ejecuta el método **Send** tiene como identificador único 33574638. El seguimiento de salida del método incluye el valor devuelto (61 en el ejemplo anterior).  
  
 Los seguimientos de red pueden capturar el tráfico de red que se envía desde la aplicación o que se recibe en esta mediante protocolos de nivel de aplicación, como el Protocolo de transferencia de hipertexto (HTTP). Estos datos se pueden capturar como texto y, opcionalmente, como datos hexadecimales. Los datos hexadecimales están disponibles cuando se especifica **includehex** como valor del atributo **tracemode**. (Para obtener información detallada sobre este atributo, vea [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) (Cómo: configurar el seguimiento de red)). El seguimiento del ejemplo siguiente se ha generado con **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Para omitir los datos hexadecimales, especifique **protocolonly** como valor del atributo **tracemode**. En el ejemplo siguiente se muestra el seguimiento cuando se especifica **protocolonly**.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a>Vea también  
 [Habilitar el seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Cómo: configurar el seguimiento de red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](../../../docs/framework/network-programming/network-tracing.md)

