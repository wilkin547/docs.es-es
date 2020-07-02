---
title: Operaciones de canalización en .NET
description: 'Descubra las operaciones de canalización en .NET. Las canalizaciones ofrecen recursos para la comunicación entre procesos. Hay dos tipos de canalizaciones: canalizaciones anónimas y con nombre.'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 35a3910bbab1b34f085a55524be0b18b3fa81958
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768890"
---
# <a name="pipe-operations-in-net"></a>Operaciones de canalización en .NET
Las canalizaciones ofrecen recursos para la comunicación entre procesos. Hay dos tipos de canalizaciones:  
  
- Canalizaciones anónimas.  
  
     Las canalizaciones anónimas permiten la comunicación entre procesos en un equipo local. Las canalizaciones anónimas requieren menos sobrecarga que las canalizaciones con nombre, pero ofrecen servicios limitados. Las canalizaciones anónimas son unidireccionales y no se puede usar a través de una red. Admiten solo una única instancia de servidor. Las canalizaciones anónimas son útiles para la comunicación entre subprocesos, o entre procesos primarios y secundarios, donde los identificadores de canalización pueden pasarse con facilidad al proceso secundario cuando se crea.  
  
     En .NET, las canalizaciones anónimas se implementan mediante el uso de las clases <xref:System.IO.Pipes.AnonymousPipeServerStream> y <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     Vea [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Canalizaciones con nombre.  
  
     Las canalizaciones con nombre permiten la comunicación entre procesos entre un servidor de canalización y uno o varios clientes de canalización. Las canalizaciones con nombre pueden ser unidireccionales o dúplex. Admiten la comunicación basada en mensajes y permiten que varios clientes se conecten simultáneamente al proceso de servidor utilizando el mismo nombre de canalización. Las canalizaciones con nombre también admiten la suplantación, que permite que los procesos de conexión usen sus propios permisos en servidores remotos.  
  
     En .NET, las canalizaciones con nombre se implementan mediante el uso de las clases <xref:System.IO.Pipes.NamedPipeServerStream> y <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     Vea [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Vea también

- [E/S de archivos y secuencias](index.md)
- [Cómo: Usar canalizaciones anónimas para la comunicación local entre procesos](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [Cómo: Usar canalizaciones con nombre para la comunicación de red entre procesos](how-to-use-named-pipes-for-network-interprocess-communication.md)
