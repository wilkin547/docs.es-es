---
title: "Interpretar el seguimiento de red | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "TraceMode (atributo)"
  - "datos hexadecimales, resultado del seguimiento de red"
  - "seguimiento de red, analizar"
  - "protocolonly"
  - "texto, resultado del seguimiento de red"
  - "includehex"
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Interpretar el seguimiento de red
Cuando se habilita la traza de la red, puede utilizar el seguimiento para capturar las llamadas que la aplicación crea a diferente <xref:System.Net> miembros de clase.  La salida de las llamadas puede ser similar a los ejemplos siguientes.  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 En el ejemplo anterior, \[588\] es el identificador único del subproceso actual.  \(4357\) y \(4387\) son las marcas de tiempo que representan el número de milisegundos transcurridos desde que la aplicación iniciada.  Los datos que sigue la marca de tiempo se muestra la aplicación que entra y salir del método **Socket.Send**.  El objeto que ejecuta el método de **Enviar** tiene 33574638 como identificador único.  El seguimiento de la salida del método incluye el valor devuelto \(61 en el ejemplo anterior\).  
  
 Los seguimientos de red pueden capturar el tráfico de red del que se envía o es recibido por la aplicación mediante protocolos en la aplicación como protocolo HTTP \(Hypertext Transfer Protocol\).  Estos datos se pueden capturar como texto y, opcionalmente, datos hexadecimales.  Los datos hexadecimal está disponible cuando se especifica **includehex** como valor del atributo de **tracemode** .  \(Para obtener información detallada sobre este atributo, vea [Cómo: Configurar la traza de la red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).\) El seguimiento del ejemplo siguiente se generó utilizando **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Para omitir datos hexadecimales, especifique **protocolonly** como valor para el atributo de **tracemode** .  El ejemplo siguiente muestra el seguimiento cuando se especifica **protocolonly** .  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## Vea también  
 [Habilitación del seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Cómo: Configurar la traza de la red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [Traza de la red en .NET Framework](../../../docs/framework/network-programming/network-tracing.md)