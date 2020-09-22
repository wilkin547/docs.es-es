---
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 07c09d0dfcb374b974fbda9099c4e85d6d054753
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870907"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>Es necesaria una referencia al ensamblado '\<assemblyname>' que contenga la clase base '\<classname>'

Es necesaria una referencia al ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '. Agregue una al proyecto.  
  
 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador Visual Basic requiere una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o ensamblado.  
  
 **Identificador de error:** BC30007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.  
  
## <a name="see-also"></a>Consulte también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
