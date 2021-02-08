---
description: 'Más información acerca de: BC30996: se esperaba un inicializador'
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: a9859dc319ec53cb42785d71b21447a097ce30f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796059"
---
# <a name="bc30996-initializer-expected"></a>BC30996: se esperaba un inicializador

Ha intentado declarar una instancia de una clase usando un inicializador de objeto en el que la lista de inicialización está vacía, tal y como se muestra en el ejemplo siguiente.

 `' Not valid.`

 `' Dim aStudent As New Student With {}`

 Debe inicializarse al menos un campo o una propiedad en la lista de inicializadores, como se muestra en el ejemplo siguiente.

 `Dim aStudent As New Student With {.year = "Senior"}`

 **Identificador de error:** BC30996

## <a name="to-correct-this-error"></a>Para corregir este error

- Inicialice al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.

## <a name="see-also"></a>Vea también

- [Inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Procedimiento para declarar un objeto mediante un inicializador de objeto](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
