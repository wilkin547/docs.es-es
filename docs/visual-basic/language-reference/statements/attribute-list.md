---
title: Lista de atributos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 2399ec1342280df101e2818399e0f41f10d9606d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945085"
---
# <a name="attribute-list-visual-basic"></a>Lista de atributos (Visual Basic)
Especifica los atributos que se aplicará a un elemento de programación declarado. Los diversos atributos se separan con comas. Siguiente es la sintaxis para un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Elementos  
|||
|---|---|
|`attributemodifier`|Se requiere para los atributos aplicados al principio de un archivo de origen. Puede ser [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) o [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Obligatorio. Nombre del atributo.|
|`attributearguments`|Opcional. Lista de argumentos posicionales para este atributo. Varios argumentos están separados por comas.|
|`attributeinitializer`|Opcional. Lista de inicializadores de variable o propiedad para este atributo. Los inicializadores múltiples se separan mediante comas.|
  
## <a name="remarks"></a>Comentarios  
 Puede aplicar uno o varios atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades etc.). Los atributos aparecen en los metadatos del ensamblado, y pueden ayudarle a anotar el código o especificar el uso de un elemento de programación determinado. Puede aplicar los atributos definidos por Visual Basic y .NET Framework, y puede definir sus propios atributos.  

 Para obtener más información sobre cuándo usar los atributos, vea [información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md). Para obtener información sobre los nombres de atributo, vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
- **Selección de ubicación.** Puede aplicar atributos a elementos de programación declarados más. Para aplicar uno o varios atributos, se coloca un *bloque de atributos* al principio de la declaración del elemento. Cada entrada en la lista de atributos especifica un atributo que desea aplicar, y el modificador y los argumentos que se está usando para esta invocación del atributo.  
  
- **Corchetes angulares.** Si se proporciona una lista de atributos, debe encerrarlo entre corchetes angulares ("`<`"y"`>`").  
  
- **Parte de la declaración.** El atributo debe ser parte de la declaración de elemento, no una instrucción independiente. Puede usar la secuencia de continuación de línea (" `_`") para ampliar la instrucción de declaración en varias líneas de código fuente.  
  
- **Modificadores.** Un modificador de atributo (`Assembly` o `Module`) se requiere en cada atributo aplicado a un elemento de programación al principio de un archivo de origen. No se permiten modificadores de atributo en atributos aplicados a los elementos que no están al principio de un archivo de origen.  
  
- **Argumentos.** Todos los argumentos posicionales para un atributo deben preceder a cualquier variable o propiedad inicializadores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se aplica el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo a un esquema de definición de un `Function` procedimiento.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> indica que el procedimiento con atributos representa un punto de entrada en una biblioteca de vínculos dinámicos (DLL) no administrada. El atributo proporciona el nombre del archivo DLL como un argumento posicional y el resto de información como inicializadores de variables.  
  
## <a name="see-also"></a>Vea también

- [Ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
