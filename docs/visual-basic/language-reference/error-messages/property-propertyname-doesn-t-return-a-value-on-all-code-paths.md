---
title: La propiedad '<propertyname>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a5cb28a024274e58da1755b437d6ba4ca6712610
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661714"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>Propiedad '\<propertyname >' no devuelve un valor en todas las rutas de código
Propiedad '\<propertyname >' no devuelve un valor en todas las rutas de código. Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.  
  
 Una propiedad `Get` procedimiento tiene al menos una ruta de acceso posibles a través de su código que no devuelve un valor.  
  
 Puede devolver un valor de una propiedad `Get` procedimiento en cualquiera de las maneras siguientes:  
  
- Asigne el valor al nombre de propiedad y, a continuación, realizar un `Exit Property` instrucción.  
  
- Asigne el valor al nombre de propiedad y, a continuación, realizar el `End Get` instrucción.  
  
- Incluya el valor en un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Si el control se transfiere a `Exit Property` o `End Get` y no ha asignado ningún valor para el nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado de la propiedad tipo de datos. Para obtener más información, vea "Comportamiento" en [instrucción Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Compruebe la lógica del flujo de control y asegúrese de que asignar un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que todos los valores devueltos desde el procedimiento devuelve un valor si siempre usa el `Return` instrucción. Si lo hace, la última instrucción antes de `End Get` debe ser un `Return` instrucción.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
