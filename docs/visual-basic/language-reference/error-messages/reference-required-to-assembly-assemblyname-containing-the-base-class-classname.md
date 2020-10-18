---
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162341"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: referencia necesaria para el ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '

Es necesaria una referencia al ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '. Agregue una al proyecto.

 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador Visual Basic requiere una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o ensamblado.

 **Identificador de error:** BC30007

## <a name="to-correct-this-error"></a>Para corregir este error

- Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.

## <a name="see-also"></a>Vea también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
