---
title: "C&#243;mo: Usar canalizaciones con nombre para la comunicaci&#243;n de red entre procesos | Microsoft Docs"
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
  - "comunicación dúplex completa [.NET Framework], canalizaciones con nombre"
  - "suplantación [.NET Framework], canalizaciones con nombre"
  - "comunicación basada en mensajes [.NET Framework], canalizaciones con nombre"
  - "conexiones múltiples a través de canalizaciones con nombre"
  - "canalizaciones con nombre [.NET Framework]"
  - "comunicaciones de red [.NET Framework], canalizaciones con nombre"
  - "canalizaciones [.NET Framework]"
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Usar canalizaciones con nombre para la comunicaci&#243;n de red entre procesos
Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización.  Proporcionan más funcionalidad que las canalizaciones anónimas, que permiten la comunicación entre procesos en un equipo local.  Las canalizaciones con nombre admiten la comunicación dúplex completa a través de una red y varias instancias de servidor, la comunicación mediante mensajes y la suplantación de clientes, que permite a los procesos que se conectan utilizar su propio conjunto de permisos en servidores remotos.  
  
 Para implementar canalizaciones con nombre, use las clases <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo crear una canalización con nombre mediante la clase <xref:System.IO.Pipes.NamedPipeServerStream>.  En este ejemplo, el proceso de servidor crea cuatro subprocesos.  Cada subproceso puede aceptar una conexión de cliente.  A continuación, el proceso de cliente conectado proporciona un nombre de archivo al servidor.  Si el cliente tiene los permisos necesarios, el proceso de servidor abre el archivo y envía su contenido de vuelta al cliente.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el proceso de cliente, que utiliza la clase <xref:System.IO.Pipes.NamedPipeClientStream>.  El cliente se conecta al proceso de servidor y envía un nombre de archivo al servidor.  En el ejemplo, se utiliza la suplantación, por lo que la identidad que ejecuta la aplicación cliente debe tener permiso de acceso al archivo.  A continuación, el servidor devuelve el contenido del archivo al cliente.  El contenido del archivo se muestra en la consola.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## Programación eficaz  
 Los procesos de servidor y cliente de este ejemplo están diseñados para ejecutarse en el mismo equipo, por lo que el nombre del servidor proporcionado al objeto <xref:System.IO.Pipes.NamedPipeClientStream> es `"."`.  Si los procesos de servidor y cliente estuvieran en equipos independientes, `"."` se reemplazaría por el nombre de red del equipo que ejecuta el proceso de servidor.  
  
## Vea también  
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>   
 [Canalizaciones](../../../docs/standard/io/pipe-operations.md)   
 [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)