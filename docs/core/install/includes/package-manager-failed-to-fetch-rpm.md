---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920734"
---

Al instalar el paquete de .NET Core, puede ver un error similar a `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`. En términos generales, este error significa que la fuente de paquetes para .NET Core se está actualizando con versiones de paquetes más recientes y que debe volver a intentarlo más tarde. Durante una actualización, la fuente de paquetes no debe estar disponible durante más de 2 horas. Si recibe este error continuamente durante más de 2 horas, abra una incidencia en <https://github.com/dotnet/core/issues>.
