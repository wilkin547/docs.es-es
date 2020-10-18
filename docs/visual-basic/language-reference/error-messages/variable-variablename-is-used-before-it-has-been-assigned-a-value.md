---
title: La variable '<variablename>' se utiliza antes de ser asignada a un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 6db8626701267f2051b289b267e7b2d9da51c283
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162224"
---
# <a name="bc42104-variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>BC42104: la variable ' \<variablename> ' se usa antes de que se le haya asignado un valor

La variable ' \<variablename> ' se usa antes de que se le haya asignado un valor. Podría producirse una excepción de referencia nula en tiempo de ejecución.

 Una aplicación tiene al menos una ruta de acceso posible a través de su código que lee una variable antes de que se le asigne un valor.

 Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos. Para un tipo de datos de referencia, el valor predeterminado es [Nothing](../nothing.md). Leer una variable de referencia que tiene un valor de `Nothing` puede producir una excepción <xref:System.NullReferenceException> en algunas circunstancias.

 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42104

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe la lógica del flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control pase a cualquier instrucción que lo lea.

- Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración. Vea "Initialization" en la [instrucción Dim](../statements/dim-statement.md).

## <a name="see-also"></a>Vea también

- [Instrucción Dim](../statements/dim-statement.md)
- [Declaración de variable](../../programming-guide/language-features/variables/variable-declaration.md)
- [Solución de problemas de variables](../../programming-guide/language-features/variables/troubleshooting-variables.md)
