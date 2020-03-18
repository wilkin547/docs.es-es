---
title: 'Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706639"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="c360e-102">Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos</span><span class="sxs-lookup"><span data-stu-id="c360e-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="c360e-103">Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización.</span><span class="sxs-lookup"><span data-stu-id="c360e-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="c360e-104">Proporcionan más funcionalidad que las canalizaciones anónimas, que permiten la comunicación entre procesos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="c360e-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="c360e-105">Las canalizaciones con nombre admiten la comunicación dúplex completa a través de una red y varias instancias de servidor, la comunicación mediante mensajes y la suplantación de clientes, que permite a los procesos que se conectan utilizar su propio conjunto de permisos en servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="c360e-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="c360e-106">Para implementar canalizaciones con nombre, use las clases <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="c360e-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c360e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c360e-107">Example</span></span>  
 <span data-ttu-id="c360e-108">En el siguiente ejemplo se muestra cómo crear una canalización con nombre mediante la clase <xref:System.IO.Pipes.NamedPipeServerStream>.</span><span class="sxs-lookup"><span data-stu-id="c360e-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="c360e-109">En este ejemplo, el proceso de servidor crea cuatro subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c360e-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="c360e-110">Cada subproceso puede aceptar una conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="c360e-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="c360e-111">A continuación, el proceso de cliente conectado proporciona un nombre de archivo al servidor.</span><span class="sxs-lookup"><span data-stu-id="c360e-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="c360e-112">Si el cliente tiene los permisos necesarios, el proceso de servidor abre el archivo y envía su contenido de vuelta al cliente.</span><span class="sxs-lookup"><span data-stu-id="c360e-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="c360e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c360e-113">Example</span></span>  
 <span data-ttu-id="c360e-114">En el ejemplo siguiente se muestra el proceso de cliente, que utiliza la clase <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="c360e-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="c360e-115">El cliente se conecta al proceso de servidor y envía un nombre de archivo al servidor.</span><span class="sxs-lookup"><span data-stu-id="c360e-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="c360e-116">En el ejemplo, se utiliza la suplantación, por lo que la identidad que ejecuta la aplicación cliente debe tener permiso de acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="c360e-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="c360e-117">A continuación, el servidor devuelve el contenido del archivo al cliente.</span><span class="sxs-lookup"><span data-stu-id="c360e-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="c360e-118">El contenido del archivo se muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="c360e-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c360e-119">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c360e-119">Robust Programming</span></span>  
 <span data-ttu-id="c360e-120">Los procesos de servidor y cliente de este ejemplo están diseñados para ejecutarse en el mismo equipo, por lo que el nombre del servidor proporcionado al objeto <xref:System.IO.Pipes.NamedPipeClientStream> es `"."`.</span><span class="sxs-lookup"><span data-stu-id="c360e-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="c360e-121">Si los procesos de servidor y cliente estuvieran en equipos independientes, `"."` se reemplazaría por el nombre de red del equipo que ejecuta el proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="c360e-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c360e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c360e-122">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- <span data-ttu-id="c360e-123">[Pipes](../../../docs/standard/io/pipe-operations.md) (Operaciones de canalización de .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="c360e-123">[Pipes](../../../docs/standard/io/pipe-operations.md)</span></span>
- [<span data-ttu-id="c360e-124">Usar canalizaciones anónimas para la comunicación local entre procesos</span><span class="sxs-lookup"><span data-stu-id="c360e-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
