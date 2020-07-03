---
title: Interpretar el seguimiento de red
description: Obtenga información sobre cómo usar el seguimiento para capturar las llamadas que realiza la aplicación a varios miembros de la clase System.Net en .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 7a17e4ba14d8c5fe136667c4eb5bc5b2fd7a8242
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502371"
---
# <a name="interpreting-network-tracing"></a>Interpretar el seguimiento de red
Cuando está habilitado el seguimiento de red, puede usarlo para capturar las llamadas que la aplicación realiza a diversos miembros de clase <xref:System.Net>. La salida de estas llamadas puede ser similar a los ejemplos siguientes.  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 En el ejemplo anterior, [588] es el identificador único del subproceso actual. (4357) y (4387) son marcas de tiempo que indican el número de milisegundos que han transcurrido desde que se ha iniciado la aplicación. Los datos que aparecen después de la marca de tiempo muestran la aplicación que entra y sale del método **Socket.Send**. El objeto que ejecuta el método **Send** tiene como identificador único 33574638. El seguimiento de salida del método incluye el valor devuelto (61 en el ejemplo anterior).  
  
 Los seguimientos de red pueden capturar el tráfico de red que se envía desde la aplicación o que se recibe en esta mediante protocolos de nivel de aplicación, como el Protocolo de transferencia de hipertexto (HTTP). Estos datos se pueden capturar como texto y, opcionalmente, como datos hexadecimales. Los datos hexadecimales están disponibles cuando se especifica **includehex** como valor del atributo **tracemode**. (Para obtener información detallada sobre este atributo, vea [Cómo: Configurar el seguimiento de red](how-to-configure-network-tracing.md)). El seguimiento del ejemplo siguiente se ha generado con **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Para omitir los datos hexadecimales, especifique **protocolonly** como valor del atributo **tracemode**. En el ejemplo siguiente se muestra el seguimiento cuando se especifica **protocolonly**.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a>Vea también

- [Habilitar el seguimiento de red](enabling-network-tracing.md)
- [Cómo: Configurar el seguimiento de red](how-to-configure-network-tracing.md)
- [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](network-tracing.md)
