---
title: Contenido de un ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- assemblies [.NET Core]
- single-file assemblies
- multifile assemblies [.NET Framework]
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 9ca12ee4bd993db3dd200a3b340c220ce5188796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122531"
---
# <a name="assembly-contents"></a>Contenido de un ensamblado
En general, un ensamblado estático está formado por cuatro elementos:

- El [manifiesto del ensamblado](manifest.md), que contiene los metadatos del ensamblado.

- Los metadatos de tipos.  

- El código de lenguaje intermedio de Microsoft (MSIL) que implementa los tipos. Lo genera el compilador a partir de uno o más archivos de código fuente.

- Un conjunto de recursos.  

El manifiesto del ensamblado es el único elemento obligatorio, pero se necesitan o bien los tipos o bien los recursos para proporcionar al ensamblado una funcionalidad significativa.

En la ilustración siguiente se muestran estos elementos agrupados en un único archivo físico.

![Diagrama en el que se muestra un ensamblado de un solo archivo denominado MyAssembly.dll.](./media/contents/single-file-assembly.gif)

En esta ilustración, los tres archivos pertenecen a un ensamblado, como se describe en el manifiesto del ensamblado contenido en MyAssembly.dll. Para el sistema de archivos, se trata de tres archivos diferentes. Tenga en cuenta que el archivo Util.netmodule se compiló como módulo porque no contiene información de ensamblado. Cuando se creó el ensamblado, el manifiesto del ensamblado se agregó a MyAssembly.dll, lo que indica su relación con Util.netmodule y Graphic.bmp.

Actualmente, al diseñar el código fuente, se toman decisiones explícitas sobre cómo repartir la funcionalidad de una aplicación entre uno o más archivos. Al diseñar el código de .NET Framework, tomará decisiones similares sobre cómo dividir la funcionalidad en uno o más ensamblados.

## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](index.md)
- [Manifiesto del ensamblado](manifest.md)
- [Consideraciones de seguridad sobre ensamblados](security-considerations.md)
