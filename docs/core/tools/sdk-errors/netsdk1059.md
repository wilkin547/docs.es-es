---
title: 'NETSDK1059: El proyecto contiene la herramienta de la CLI de .NET obsoleta'
description: Procedimiento para resolver el problema de un proyecto que contiene una herramienta de la CLI de .NET obsoleta.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713124"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: El proyecto contiene la herramienta de la CLI de .NET obsoleta

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Cuando el SDK de .NET emite la advertencia NETSDK1059, el proyecto contiene una herramienta de la CLI de .NET obsoleta. A partir de .NET Core 2.1, estas herramientas se incluyen en el SDK de .NET y no es necesario que en el proyecto se les haga referencia de forma explícita. [Aquí](https://aka.ms/dotnetclitools-in-box) puede encontrar más información para migrar a .NET Core 2.1.
