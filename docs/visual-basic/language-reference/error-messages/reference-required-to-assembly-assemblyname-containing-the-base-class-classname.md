---
description: "Más información sobre: BC30007: referencia necesaria para el ensamblado ' <assemblyname> ' que contiene la clase base '<classname>"
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f01795d3e8147015f9f46697b047a8c63099ff32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792055"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: referencia necesaria para el ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '

Es necesaria una referencia al ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '. Agregue una al proyecto.

 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador Visual Basic requiere una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o ensamblado.

 **Identificador de error:** BC30007

## <a name="to-correct-this-error"></a>Para corregir este error

- Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.

## <a name="see-also"></a>Consulte también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
