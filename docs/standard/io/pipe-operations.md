---
title: "Operaciones de canalización de .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Operaciones de canalización de .NET Framework
Canalizaciones proporcionan un medio para la comunicación entre procesos. Hay dos tipos de canalizaciones:  
  
-   Canalizaciones anónimas.  
  
     Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local. Las canalizaciones anónimas ofrecen servicios limitados pero requieren una menor sobrecarga que las canalizaciones con nombre. Las canalizaciones anónimas son unidireccionales y no se puede usar a través de una red. Admite solo una única instancia del servidor. Las canalizaciones anónimas son útiles para la comunicación entre subprocesos, o entre procesos primarios y secundarios, donde los identificadores de canalización pueden pasarse con facilidad al proceso secundario cuando se crea.  
  
     En .NET Framework, las canalizaciones anónimas se implementan mediante el uso de la <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream> clases.  
  
     Vea [Cómo: usar canalizaciones anónimas para la comunicación entre procesos Local](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Canalizaciones con nombre.  
  
     Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización. Canalizaciones con nombre pueden ser unidireccional o dúplex. Se admiten la comunicación basada en mensajes y permitir que varios clientes se conecten simultáneamente al proceso de servidor utilizando el mismo nombre de canalización. Canalizaciones con nombre también admiten la suplantación, que permite que los procesos de conexión utilizar sus propios permisos en servidores remotos.  
  
     En .NET Framework, implementar canalizaciones con nombre mediante la <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream> clases.  
  
     Vea [Cómo: usar canalizaciones con nombre para la comunicación entre procesos de red](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Vea también  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)  
 [Usar canalizaciones anónimas para la comunicación local entre procesos](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Usar canalizaciones con nombre para la comunicación de red entre procesos](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
