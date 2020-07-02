---
title: Procedimiento para usar canalizaciones anónimas para la comunicación local entre procesos
description: Aprenda a usar canalizaciones anónimas para la comunicación local entre procesos en un equipo local en .NET. Las canalizaciones anónimas requieren menos sobrecarga que las canalizaciones con nombre.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
ms.openlocfilehash: 090a25aea4f280fc2ad00cf7777a501c475dfc66
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594808"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>Procedimiento para usar canalizaciones anónimas para la comunicación local entre procesos
Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local. Proporcionan menos funcionalidad que las canalizaciones con nombre, pero también tienen menos carga de procesamiento. Puede utilizar las canalizaciones anónimas para facilitar la comunicación entre procesos en un equipo local. No se puede utilizar las canalizaciones anónimas para la comunicación a través de una red.  
  
 Para implementar canalizaciones anónimas, use las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una manera de enviar una cadena de un proceso primario a un proceso secundario mediante canalizaciones anónimas. En este ejemplo se crea un objeto <xref:System.IO.Pipes.AnonymousPipeServerStream> en un proceso primario con un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection.Out>. A continuación, el proceso primario crea un proceso secundario mediante un identificador de cliente para crear un objeto <xref:System.IO.Pipes.AnonymousPipeClientStream>. El proceso secundario tiene un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection.In>.  
  
 El proceso primario envía a continuación una cadena proporcionada por usuario al proceso secundario. La cadena se muestra a la consola en el proceso secundario.  
  
 En el ejemplo siguiente se muestra el proceso del servidor.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el proceso del cliente. El proceso de servidor inicia el proceso de cliente y da un identificador de cliente a ese proceso. El ejecutable resultante del código de cliente debe denominarse `pipeClient.exe` y copiarse en el mismo directorio que el ejecutable del servidor antes de ejecutar el proceso de servidor.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>Vea también

- [Pipes](pipe-operations.md) (Operaciones de canalización de .NET Framework)
- [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](how-to-use-named-pipes-for-network-interprocess-communication.md)
