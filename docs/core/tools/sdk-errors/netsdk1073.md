---
title: 'NETSDK1073: No se ha reconocido el valor de FrameworkReference'
description: Procedimiento para resolver el problema por el que no se puede encontrar el valor de FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957114"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: No se ha reconocido el valor de FrameworkReference

**Este artículo se aplica a:** ✔️ SDK de .NET 2.1.100 y versiones posteriores

Normalmente este error significa que hay una versión de un elemento FrameworkReference concreto que el SDK no puede encontrar. Intente eliminar las carpetas *obj* y *bin*, y ejecute `dotnet restore` para volver a descargar los paquetes de destino más recientes.

Como alternativa, es posible que haya un problema con la instalación, por lo que debe asegurarse de tener las versiones más recientes de .NET y Visual Studio.
