---
title: '#pragma: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 8b39d6760a5e30986d5d4bbe9bb1281dbf6742a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471018"
---
# <a name="pragma-c-reference"></a>#pragma (Referencia de C#)
`#pragma` proporciona al compilador instrucciones especiales para la compilación del archivo en el que aparece. Las instrucciones deben ser compatibles con el compilador. En otras palabras, no puede usar `#pragma` para crear instrucciones de preprocesamiento personalizadas. El compilador de Microsoft C# admite las siguientes dos instrucciones `#pragma`:  
  
 [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Parámetros  
 `pragma-name`  
 El nombre de una pragma reconocida.  
  
 `pragma-arguments`  
 Argumentos específicos de pragma.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
- [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
