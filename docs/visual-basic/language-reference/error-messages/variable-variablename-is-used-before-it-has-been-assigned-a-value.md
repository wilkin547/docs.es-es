---
description: "Más información acerca de: BC42104: la variable ' <variablename> ' se usa antes de que se le haya asignado un valor"
title: La variable '<variablename>' se utiliza antes de ser asignada a un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 501c3e3971c5ca0ebdba6981134f5029b77d0075
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701500"
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
