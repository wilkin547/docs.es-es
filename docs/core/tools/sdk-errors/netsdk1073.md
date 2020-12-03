---
title: 'NETSDK1073: No se ha reconocido el valor de FrameworkReference'
description: Procedimiento para resolver el problema por el que no se puede encontrar el valor de FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713033"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: No se ha reconocido el valor de FrameworkReference

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Normalmente este error significa que hay una versión de un elemento FrameworkReference concreto que el SDK no puede encontrar. Intente eliminar las carpetas *obj* y *bin*, y ejecute `dotnet restore` para volver a descargar los paquetes de destino más recientes.

Como alternativa, es posible que haya un problema con la instalación, por lo que debe asegurarse de tener las versiones más recientes de .NET y Visual Studio.
