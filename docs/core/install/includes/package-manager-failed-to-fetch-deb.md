---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920661"
---

Al instalar el paquete de .NET Core, puede ver un error similar a `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`. En términos generales, este error significa que la fuente de paquetes para .NET Core se está actualizando con versiones de paquetes más recientes y que debe volver a intentarlo más tarde. Durante una actualización, la fuente de paquetes no debe estar disponible durante más de 30 minutos. Si recibe este error continuamente durante más de 30 minutos, abra una incidencia en <https://github.com/dotnet/core/issues>.
