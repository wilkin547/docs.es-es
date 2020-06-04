---
title: "'<typename>' es un tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 7056bbf2b4de26feba3bfbe0e02b3239311271c9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382177"
---
# <a name="typename-is-a-delegate-type"></a>'\<typename>' es un tipo delegado
' \<typename> ' es un tipo de delegado. La construcción de delegado solo permite una expresión AddressOf como una lista de argumentos. A menudo se puede usar una expresión AddressOf en lugar de una construcción de delegado.  
  
 Una `New` cláusula que crea una instancia de una clase delegada proporciona una lista de argumentos no válidos al constructor delegado.  
  
 Solo se puede proporcionar una `AddressOf` expresión cuando se crea una nueva instancia de delegado.  
  
 Este error puede producirse si no se pasan argumentos al constructor delegado, si se pasa más de un argumento, o si se pasa un solo argumento que no es una `AddressOf` expresión válida.  
  
 **Identificador de error:** BC32008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use una sola `AddressOf` expresión en la lista de argumentos para la clase Delegate en la `New` cláusula.  
  
## <a name="see-also"></a>Consulte también

- [New (operador)](../operators/new-operator.md)
- [AddressOf (operador)](../operators/addressof-operator.md)
- [Delegados](../../programming-guide/language-features/delegates/index.md)
- [Procedimiento para invocar un método delegado](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
