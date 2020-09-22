---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873600"
---
# <a name="optional-expected"></a>Se esperaba 'Optional'

Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario. Cada argumento que siga a un argumento opcional también debe ser opcional.  
  
 **Identificador de error:** BC30202  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si el argumento está pensado para ser necesario, muévalo para que preceda al primer argumento opcional de la lista de argumentos.  
  
2. Si el argumento está pensado para ser opcional, use la `Optional` palabra clave.  
  
## <a name="see-also"></a>Consulte también

- [Parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md)
