---
title: Lista de atributos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 771757afe214919649e13fda3990e1154be8e1e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004532"
---
# <a name="attribute-list-visual-basic"></a>Lista de atributos (Visual Basic)
Especifica los atributos que se van a aplicar a un elemento de programación declarado. Los diversos atributos se separan con comas. A continuación se encuentra la sintaxis de un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Elementos  
|||
|---|---|
|`attributemodifier`|Se requiere para los atributos aplicados al principio de un archivo de código fuente. Puede ser un [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) o un [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Obligatorio. Nombre del atributo.|
|`attributearguments`|Opcional. Lista de argumentos posicionales para este atributo. Los argumentos múltiples se separan mediante comas.|
|`attributeinitializer`|Opcional. Lista de inicializadores de variable o propiedad para este atributo. Los inicializadores múltiples se separan mediante comas.|
  
## <a name="remarks"></a>Comentarios  
 Puede aplicar uno o varios atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades, etc.). Los atributos aparecen en los metadatos del ensamblado y pueden ayudarle a anotar el código o especificar cómo usar un elemento de programación determinado. Puede aplicar atributos definidos por Visual Basic y el .NET Framework, y puede definir sus propios atributos.  

 Para obtener más información sobre Cuándo usar atributos, vea [información general sobre los atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md). Para obtener información sobre los nombres de atributo, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
- **Ubicación.** Puede aplicar atributos a la mayoría de los elementos de programación declarados. Para aplicar uno o varios atributos, coloque un *bloque de atributos* al principio de la declaración del elemento. Cada entrada de la lista de atributos especifica un atributo que se desea aplicar y el modificador y los argumentos que se usan para esta invocación del atributo.  
  
- **Corchetes angulares.** Si proporciona una lista de atributos, debe encerrarla entre corchetes angulares ("`<`" y "`>`").  
  
- **Parte de la declaración.** El atributo debe formar parte de la declaración del elemento, no de una instrucción independiente. Puede usar la secuencia de continuación de línea ("`_`") para extender la instrucción de declaración en varias líneas de código fuente.  
  
- **Modificadores.** Se requiere un modificador de atributo (`Assembly` o `Module`) en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente. No se permiten modificadores de atributo en los atributos aplicados a los elementos que no están al principio de un archivo de código fuente.  
  
- **Argumentos.** Todos los argumentos posicionales de un atributo deben preceder a cualquier inicializador de variable o propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se aplica el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> a una definición de esquema de un procedimiento `Function`.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> indica que el procedimiento con atributos representa un punto de entrada de una biblioteca de vínculos dinámicos (DLL) no administrada. El atributo proporciona el nombre del archivo DLL como argumento posicional y la otra información como inicializadores de variables.  
  
## <a name="see-also"></a>Vea también

- [Ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
