---
title: Contenido de los ensamblados
description: En este artículo se describe el contenido de un ensamblado .NET, que puede incluir metadatos de ensamblado, metadatos de tipo, código MSIL y recursos.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 94df452162ed7290fab7fa267d2624e6d844a587
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378566"
---
# <a name="assembly-contents"></a>Contenido de los ensamblados

En general, un ensamblado estático está formado por cuatro elementos:

- El [manifiesto del ensamblado](manifest.md), que contiene los metadatos del ensamblado.

- Los metadatos de tipos.  

- El código de lenguaje intermedio de Microsoft (MSIL) que implementa los tipos. Lo genera el compilador a partir de uno o más archivos de código fuente.

- Un conjunto de [recursos](../../framework/resources/index.md).  

El manifiesto del ensamblado es el único elemento obligatorio, pero se necesitan o bien los tipos o bien los recursos para proporcionar al ensamblado una funcionalidad significativa.

En la siguiente ilustración se muestran estos elementos agrupados en un único archivo físico:

![Un ensamblado de un solo archivo denominado MAssembly.dll](./media/contents/single-file-assembly.gif)

A diseñar el código fuente, se toman decisiones explícitas sobre cómo repartir la funcionalidad de una aplicación entre uno o más archivos. Al diseñar código .NET, tomará decisiones similares sobre cómo dividir la funcionalidad en uno o más ensamblados.

## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](index.md)
- [Manifiesto del ensamblado](manifest.md)
- [Consideraciones de seguridad sobre ensamblados](security-considerations.md)
