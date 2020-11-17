---
title: Advertencia SYSLIB0010
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0010.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 824423d58802d4a286bfed98422341097985990f
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440613"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010: API de comunicación remota no compatibles

[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) es una tecnología heredada; la infraestructura solo existe en .NET Framework. Las siguientes API relacionadas con la comunicación remota se han marcado como obsoletas a partir de .NET 5.0. Su empleo en el código genera una advertencia `SYSLIB0010` en tiempo de compilación.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluciones alternativas

Considere la posibilidad de usar servicios REST basados en WCF o HTTP para comunicarse con objetos de otras aplicaciones o entre máquinas. Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../porting/net-framework-tech-unavailable.md).

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
