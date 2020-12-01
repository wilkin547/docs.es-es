---
title: Operaciones de canalización en .NET
description: 'Descubra las operaciones de canalización en .NET. Las canalizaciones ofrecen recursos para la comunicación entre procesos. Hay dos tipos de canalizaciones: canalizaciones anónimas y con nombre.'
ms.date: 03/30/2017
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: bb8804c32b9f2b54b05298779bddae117c10dcf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734808"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="d8a4a-105">Operaciones de canalización en .NET</span><span class="sxs-lookup"><span data-stu-id="d8a4a-105">Pipe Operations in .NET</span></span>

<span data-ttu-id="d8a4a-106">Las canalizaciones ofrecen recursos para la comunicación entre procesos.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-106">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="d8a4a-107">Hay dos tipos de canalizaciones:</span><span class="sxs-lookup"><span data-stu-id="d8a4a-107">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="d8a4a-108">Canalizaciones anónimas.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-108">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="d8a4a-109">Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-109">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="d8a4a-110">Las canalizaciones anónimas requieren menos sobrecarga que las canalizaciones con nombre, pero ofrecen servicios limitados.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-110">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="d8a4a-111">Las canalizaciones anónimas son unidireccionales y no se puede usar a través de una red.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-111">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="d8a4a-112">Admiten solo una única instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-112">They support only a single server instance.</span></span> <span data-ttu-id="d8a4a-113">Las canalizaciones anónimas son útiles para la comunicación entre subprocesos, o entre procesos primarios y secundarios, donde los identificadores de canalización pueden pasarse con facilidad al proceso secundario cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-113">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="d8a4a-114">En .NET, las canalizaciones anónimas se implementan mediante el uso de las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-114">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="d8a4a-115">Vea [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="d8a4a-115">See [How to: Use Anonymous Pipes for Local Interprocess Communication](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="d8a4a-116">Canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-116">Named pipes.</span></span>  
  
     <span data-ttu-id="d8a4a-117">Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-117">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="d8a4a-118">Las canalizaciones con nombre pueden ser unidireccionales o dúplex.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-118">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="d8a4a-119">Admiten la comunicación basada en mensajes y permiten que varios clientes se conecten simultáneamente al proceso de servidor utilizando el mismo nombre de canalización.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-119">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="d8a4a-120">Las canalizaciones con nombre también admiten la suplantación, que permite que los procesos de conexión usen sus propios permisos en servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-120">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="d8a4a-121">En .NET, las canalizaciones con nombre se implementan mediante el uso de las clases <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="d8a4a-121">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="d8a4a-122">Vea [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="d8a4a-122">See [How to: Use Named Pipes for Network Interprocess Communication](how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a4a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8a4a-123">See also</span></span>

- [<span data-ttu-id="d8a4a-124">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="d8a4a-124">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="d8a4a-125">Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos</span><span class="sxs-lookup"><span data-stu-id="d8a4a-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="d8a4a-126">Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos</span><span class="sxs-lookup"><span data-stu-id="d8a4a-126">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
