---
title: 'NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos'
description: Procedimiento para resolver el problema de la falta de un destino en un archivo de recursos.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 207c8b0274c13e7af594e05cfac2a95907f85b81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717908"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Cuando el SDK de .NET emite el error NETSDK1005 o NETSDK1047, falta información sobre una de las plataformas de destino en el archivo de recursos del proyecto. Normalmente, para corregir esto debe asegurarse de que se ejecute la restauración y de que el valor de destino que falta está incluido en la propiedad `TargetFrameworks` del proyecto.

> [!NOTE]
> Ha habido un problema conocido con las primeras compilaciones de .NET 5 Preview 8 cuando se usaba con versiones de vista previa de Visual Studio 16.8 en las que se producía este error. En concreto, si el destino que falta es `net5.0-windows7.0` o `net5.0`, asegúrese de que ha actualizado a las versiones más recientes de Visual Studio y el SDK de .NET 5.
