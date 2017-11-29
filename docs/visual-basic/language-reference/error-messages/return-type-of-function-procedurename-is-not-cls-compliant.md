---
title: "Valor devuelto de función &#39; &lt;nombreProcedimiento&gt;&#39; no es conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords: BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16670521ec09ae9cab28bf6ca4705c131fd84701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>Valor devuelto de función &#39; &lt;nombreProcedimiento&gt;&#39; no es conforme a CLS
A `Function` procedimiento está marcado como `<CLSCompliant(True)>` pero devuelve un tipo que está marcado como `<CLSCompliant(False)>`, no está marcado o no cumple los requisitos porque es un tipo no compatible.  
  
 Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), solo debe usar tipos conformes a CLS. Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.  
  
 Los siguientes tipos de datos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no son conformes con CLS:  
  
-   [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40027  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el `Function` procedimiento debe devolver este tipo determinado, quite el <xref:System.CLSCompliantAttribute>. El procedimiento no puede ser conforme a CLS.  
  
-   Si el `Function` procedimiento debe ser conforme a CLS, cambie el tipo de valor devuelto al tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Por ejemplo, `int` suele ser de 16 bits en otros entornos. Si va a devolver un entero de 16 bits a esos componentes, declárelo como `Short` en lugar de `Integer` en su administrado [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código.  
  
## <a name="see-also"></a>Vea también  
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
