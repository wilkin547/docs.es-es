---
title: Lista de atributos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 35d031722a5eddd6adce5e32df62b86c500d305b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="attribute-list-visual-basic"></a>Lista de atributos (Visual Basic)
Especifica los atributos que se aplicará a un elemento de programación declarado. Los diversos atributos se separan con comas. A continuación se muestra la sintaxis para un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Elementos  
 `attributemodifier`  
 Obligatorio para atributos aplicados al principio de un archivo de código fuente. Puede ser [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) o [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Requerido. Nombre del atributo.  
  
 `attributearguments`  
 Opcional. Lista de argumentos posicionales para este atributo. Varios argumentos están separados por comas.  
  
 `attributeinitializer`  
 Opcional. Lista de inicializadores de variable o propiedad para este atributo. Inicializadores múltiples se separan por comas.  
  
## <a name="remarks"></a>Comentarios  
 Puede aplicar uno o más atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades y así sucesivamente). Los atributos aparecen en los metadatos del ensamblado, y pueden ayudarle a anotar el código o especificar cómo se utiliza un elemento de programación determinado. Puede aplicar atributos definidos por Visual Basic y .NET Framework, y puede definir sus propios atributos.  

 Para obtener más información sobre cuándo utilizar los atributos, vea [información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md). Para obtener información sobre nombres de atributo, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Selección de ubicación.** Puede aplicar atributos a elementos de programación más declarados. Para aplicar uno o más atributos, coloque un *bloque de atributos* al principio de la declaración del elemento. Cada entrada de la lista de atributos especifica un atributo que se va a aplicar, y el modificador y argumentos que está utilizando para esta invocación del atributo.  
  
-   **Corchetes angulares.** Si se proporciona una lista de atributos, debe encerrar entre corchetes angulares ("`<`"y"`>`").  
  
-   **Parte de la declaración.** El atributo debe formar parte de la declaración del elemento, no una instrucción independiente. Puede usar la secuencia de continuación de línea (" `_`") para ampliar la instrucción de declaración en varias líneas de código fuente.  
  
-   **Modificadores.** Un modificador de atributo (`Assembly` o `Module`) es necesario en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente. No se permiten modificadores de atributo en atributos aplicados a los elementos que no están al principio de un archivo de origen.  
  
-   **Argumentos.** Todos los argumentos posicionales para un atributo deben preceder a cualquier inicializador de variable o propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente aplica el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo a un esquema de definición de un `Function` procedimiento.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> indica que el procedimiento con atributos representa un punto de entrada en una biblioteca de vínculos dinámicos (DLL) no administrada. El atributo proporciona el nombre de archivo DLL como un argumento de posición y el resto de información como inicializadores de variables.  
  
## <a name="see-also"></a>Vea también  
 [Ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
