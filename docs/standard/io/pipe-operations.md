---
title: "Operaciones de canalizaci&#243;n de .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "canalizaciones [.NET Framework]"
  - "operaciones de canalización [.NET Framework]"
  - "comunicación entre procesos [.NET Framework], canalizaciones"
  - "E/S [.NET Framework], canalizaciones"
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Operaciones de canalizaci&#243;n de .NET Framework
Las canalizaciones son un medio de comunicación entre procesos.  Existen dos tipos de canalizaciones:  
  
-   Canalizaciones anónimas.  
  
     Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local.  Las canalizaciones anónimas ofrecen servicios limitados pero requieren menos esfuerzo que las canalizaciones con nombre.  Las canalizaciones anónimas son unidireccionales y no se pueden utilizar a través de una red.  Sólo admiten una instancia de servidor única.  Las canalizaciones anónimas son útiles para la comunicación entre subprocesos o entre procesos primarios y secundarios en la que se puede pasar los identificadores de canalización con facilidad al proceso secundario cuando se crea.  
  
     En .NET Framework, implemente canalizaciones anónimas mediante clases de <xref:System.IO.Pipes.AnonymousPipeServerStream> y de <xref:System.IO.Pipes.AnonymousPipeClientStream> .  
  
     Vea [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Canalizaciones con nombre.  
  
     Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización.  Las canalizaciones con nombre pueden ser unidireccionales o dúplex.  Admiten la comunicación mediante mensajes y permiten que varios clientes se conecten simultáneamente al proceso de servidor utilizando el mismo nombre de canalización.  Las canalizaciones con nombre también admiten la suplantación, que permite a los procesos que se conectan utilizar sus propios permisos en servidores remotos.  
  
     En .NET Framework, las canalizaciones con nombre se implementan mediante las clases de <xref:System.IO.Pipes.NamedPipeServerStream> y de <xref:System.IO.Pipes.NamedPipeClientStream> .  
  
     Vea [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## Vea también  
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)   
 [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)