---
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 54848fdbd2547fe021f0386843f9666760396cb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013782"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>Necesaria una referencia al ensamblado '\<assemblyname >' que contiene la clase base\<classname >'
Necesaria una referencia al ensamblado '\<assemblyname >' que contiene la clase base\<classname >'. Agregue una al proyecto.  
  
 La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador de Visual Basic requiere una referencia para evitar la ambigüedad en caso de la clase está definida en más de una DLL o ensamblado.  
  
 **Identificador de error:** BC30007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.  
  
## <a name="see-also"></a>Vea también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
