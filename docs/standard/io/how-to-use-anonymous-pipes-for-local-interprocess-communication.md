---
title: 'Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos'
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
ms.openlocfilehash: 9962471697888041e98e38dd5f7feaecc306894d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291791"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="55f20-102">Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos</span><span class="sxs-lookup"><span data-stu-id="55f20-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="55f20-103">Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="55f20-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="55f20-104">Proporcionan menos funcionalidad que las canalizaciones con nombre, pero también tienen menos carga de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="55f20-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="55f20-105">Puede utilizar las canalizaciones anónimas para facilitar la comunicación entre procesos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="55f20-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="55f20-106">No se puede utilizar las canalizaciones anónimas para la comunicación a través de una red.</span><span class="sxs-lookup"><span data-stu-id="55f20-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="55f20-107">Para implementar canalizaciones anónimas, use las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="55f20-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55f20-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55f20-108">Example</span></span>  
 <span data-ttu-id="55f20-109">En el ejemplo siguiente se muestra una manera de enviar una cadena de un proceso primario a un proceso secundario mediante canalizaciones anónimas.</span><span class="sxs-lookup"><span data-stu-id="55f20-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="55f20-110">En este ejemplo se crea un objeto <xref:System.IO.Pipes.AnonymousPipeServerStream> en un proceso primario con un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="55f20-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="55f20-111">A continuación, el proceso primario crea un proceso secundario mediante un identificador de cliente para crear un objeto <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="55f20-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="55f20-112">El proceso secundario tiene un valor <xref:System.IO.Pipes.PipeDirection> de <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="55f20-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="55f20-113">El proceso primario envía a continuación una cadena proporcionada por usuario al proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="55f20-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="55f20-114">La cadena se muestra a la consola en el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="55f20-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="55f20-115">En el ejemplo siguiente se muestra el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="55f20-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="55f20-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55f20-116">Example</span></span>  
 <span data-ttu-id="55f20-117">En el ejemplo siguiente se muestra el proceso del cliente.</span><span class="sxs-lookup"><span data-stu-id="55f20-117">The following example shows the client process.</span></span> <span data-ttu-id="55f20-118">El proceso de servidor inicia el proceso de cliente y da un identificador de cliente a ese proceso.</span><span class="sxs-lookup"><span data-stu-id="55f20-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="55f20-119">El ejecutable resultante del código de cliente debe denominarse `pipeClient.exe` y copiarse en el mismo directorio que el ejecutable del servidor antes de ejecutar el proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="55f20-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="55f20-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="55f20-120">See also</span></span>

- <span data-ttu-id="55f20-121">[Pipes](pipe-operations.md) (Operaciones de canalización de .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="55f20-121">[Pipes](pipe-operations.md)</span></span>
- [<span data-ttu-id="55f20-122">Usar canalizaciones con nombre para la comunicación de red entre procesos</span><span class="sxs-lookup"><span data-stu-id="55f20-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
