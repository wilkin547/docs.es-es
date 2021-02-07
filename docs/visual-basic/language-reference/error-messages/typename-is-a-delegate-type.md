---
description: "Más información acerca de: BC32008: ' <typename> ' es un tipo delegado"
title: "'<typename>' es un tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 72aac48038c433b7938c54e7f1138a5b91bf7689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675031"
---
# <a name="bc32008-typename-is-a-delegate-type"></a>BC32008: ' \<typename> ' es un tipo delegado

' \<typename> ' es un tipo de delegado. La construcción de delegado solo permite una expresión AddressOf como una lista de argumentos. A menudo se puede usar una expresión AddressOf en lugar de una construcción de delegado.

 Una `New` cláusula que crea una instancia de una clase delegada proporciona una lista de argumentos no válidos al constructor delegado.

 Solo se puede proporcionar una `AddressOf` expresión cuando se crea una nueva instancia de delegado.

 Este error puede producirse si no se pasan argumentos al constructor delegado, si se pasa más de un argumento, o si se pasa un solo argumento que no es una `AddressOf` expresión válida.

 **Identificador de error:** BC32008

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una sola `AddressOf` expresión en la lista de argumentos para la clase Delegate en la `New` cláusula.

## <a name="see-also"></a>Vea también

- [New Operator (Nuevo operador)](../operators/new-operator.md)
- [Operador AddressOf](../operators/addressof-operator.md)
- [Delegados](../../programming-guide/language-features/delegates/index.md)
- [Procedimiento para invocar un método delegado](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
