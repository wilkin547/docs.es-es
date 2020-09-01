---
description: '#pragma: Referencia de C#'
title: '#pragma: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 97d7a786c83a8be21f7fd38873061dba0f9278ae
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137960"
---
# <a name="pragma-c-reference"></a>#pragma (Referencia de C#)
`#pragma` proporciona al compilador instrucciones especiales para la compilación del archivo en el que aparece. Las instrucciones deben ser compatibles con el compilador. En otras palabras, no puede usar `#pragma` para crear instrucciones de preprocesamiento personalizadas. El compilador de Microsoft C# admite las siguientes dos instrucciones `#pragma`:  
  
 [#pragma warning](./preprocessor-pragma-warning.md)  
  
 [#pragma checksum](./preprocessor-pragma-checksum.md)  
  
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

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
- [#pragma warning](./preprocessor-pragma-warning.md)
- [#pragma checksum](./preprocessor-pragma-checksum.md)
