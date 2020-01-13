---
title: Operaciones de canalización en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 693dd1eb0b0b9bb87973eead26a344ed67641e34
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706561"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="4f9bb-102">Operaciones de canalización en .NET</span><span class="sxs-lookup"><span data-stu-id="4f9bb-102">Pipe Operations in .NET</span></span>
<span data-ttu-id="4f9bb-103">Las canalizaciones ofrecen recursos para la comunicación entre procesos.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="4f9bb-104">Hay dos tipos de canalizaciones:</span><span class="sxs-lookup"><span data-stu-id="4f9bb-104">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="4f9bb-105">Canalizaciones anónimas.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="4f9bb-106">Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="4f9bb-107">Las canalizaciones anónimas requieren menos sobrecarga que las canalizaciones con nombre, pero ofrecen servicios limitados.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="4f9bb-108">Las canalizaciones anónimas son unidireccionales y no se puede usar a través de una red.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="4f9bb-109">Admiten solo una única instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-109">They support only a single server instance.</span></span> <span data-ttu-id="4f9bb-110">Las canalizaciones anónimas son útiles para la comunicación entre subprocesos, o entre procesos primarios y secundarios, donde los identificadores de canalización pueden pasarse con facilidad al proceso secundario cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="4f9bb-111">En .NET, las canalizaciones anónimas se implementan mediante el uso de las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-111">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="4f9bb-112">Vea [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="4f9bb-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="4f9bb-113">Canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-113">Named pipes.</span></span>  
  
     <span data-ttu-id="4f9bb-114">Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="4f9bb-115">Las canalizaciones con nombre pueden ser unidireccionales o dúplex.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="4f9bb-116">Admiten la comunicación basada en mensajes y permiten que varios clientes se conecten simultáneamente al proceso de servidor utilizando el mismo nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="4f9bb-117">Las canalizaciones con nombre también admiten la suplantación, que permite que los procesos de conexión usen sus propios permisos en servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="4f9bb-118">En .NET, las canalizaciones con nombre se implementan mediante el uso de las clases <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="4f9bb-118">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="4f9bb-119">Vea [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="4f9bb-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9bb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f9bb-120">See also</span></span>

- [<span data-ttu-id="4f9bb-121">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="4f9bb-121">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="4f9bb-122">Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos</span><span class="sxs-lookup"><span data-stu-id="4f9bb-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="4f9bb-123">Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos</span><span class="sxs-lookup"><span data-stu-id="4f9bb-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
