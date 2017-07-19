---
title: "C&#243;mo: Usar canalizaciones an&#243;nimas para la comunicaci&#243;n local entre procesos | Microsoft Docs"
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
  - "canalizaciones anónimas [.NET Framework]"
  - "comunicación de equipo local [.NET Framework], canalizaciones"
  - "comunicación unidireccional [.NET Framework]"
  - "comunicación primaria-secundaria [.NET Framework]"
  - "canalizaciones [.NET Framework]"
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Usar canalizaciones an&#243;nimas para la comunicaci&#243;n local entre procesos
Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local.  Proporcionan menos funcionalidad que las canalizaciones con nombre, pero también tienen menos carga de procesamiento.  Puede utilizar las canalizaciones anónimas para facilitar la comunicación entre procesos en un equipo local.  No se puede utilizar las canalizaciones anónimas para la comunicación a través de una red.  
  
 Para implementar canalizaciones anónimas, use las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una manera de enviar una cadena de un proceso primario a un proceso secundario mediante canalizaciones anónimas.  En este ejemplo se crea un objeto <xref:System.IO.Pipes.AnonymousPipeServerStream> en un proceso primario con un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection>.  A continuación, el proceso primario crea un proceso secundario mediante un identificador de cliente para crear un objeto <xref:System.IO.Pipes.AnonymousPipeClientStream>.  El proceso secundario tiene un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection>.  
  
 El proceso primario envía a continuación una cadena proporcionada por usuario al proceso secundario.  La cadena se muestra a la consola en el proceso secundario.  
  
 En el ejemplo siguiente se muestra el proceso del servidor.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el proceso del cliente.  El proceso de servidor inicia el proceso de cliente y da un identificador de cliente a ese proceso.  El ejecutable resultante del código de cliente debe denominarse `pipeClient.exe` y copiarse en el mismo directorio que el ejecutable del servidor antes de ejecutar el proceso de servidor.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## Vea también  
 [Canalizaciones](../../../docs/standard/io/pipe-operations.md)   
 [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)