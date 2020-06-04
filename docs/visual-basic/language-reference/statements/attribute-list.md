---
title: Lista de atributos
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: f2400334182d373ea49c130fd17bc4f9943248d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408450"
---
# <a name="attribute-list-visual-basic"></a>Lista de atributos (Visual Basic)
Especifica los atributos que se van a aplicar a un elemento de programación declarado. Los diversos atributos se separan con comas. A continuación se encuentra la sintaxis de un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Partes  
|||
|---|---|
|`attributemodifier`|Se requiere para los atributos aplicados al principio de un archivo de código fuente. Puede ser un [ensamblado](../modifiers/assembly.md) o un [módulo](../modifiers/module-keyword.md).|
|`attributename`| Necesario. Nombre del atributo.|
|`attributearguments`|Opcional. Lista de argumentos posicionales para este atributo. Los argumentos múltiples se separan mediante comas.|
|`attributeinitializer`|Opcional. Lista de inicializadores de variable o propiedad para este atributo. Los inicializadores múltiples se separan mediante comas.|
  
## <a name="remarks"></a>Observaciones  
 Puede aplicar uno o varios atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades, etc.). Los atributos aparecen en los metadatos del ensamblado y pueden ayudarle a anotar el código o especificar cómo usar un elemento de programación determinado. Puede aplicar atributos definidos por Visual Basic y el .NET Framework, y puede definir sus propios atributos.  

 Para obtener más información sobre Cuándo usar atributos, vea [información general sobre los atributos](../../programming-guide/concepts/attributes/index.md). Para obtener información sobre los nombres de atributo, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
- **Ubicación.** Puede aplicar atributos a la mayoría de los elementos de programación declarados. Para aplicar uno o varios atributos, coloque un *bloque de atributos* al principio de la declaración del elemento. Cada entrada de la lista de atributos especifica un atributo que se desea aplicar y el modificador y los argumentos que se usan para esta invocación del atributo.  
  
- **Corchetes angulares.** Si proporciona una lista de atributos, debe encerrarla entre corchetes angulares (" `<` " y " `>` ").  
  
- **Parte de la declaración.** El atributo debe formar parte de la declaración del elemento, no de una instrucción independiente. Puede usar la secuencia de continuación de línea (" `_` ") para extender la instrucción de declaración en varias líneas de código fuente.  
  
- **Modificadores.** Se requiere un modificador `Assembly` de atributo (o `Module` ) en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente. No se permiten modificadores de atributo en los atributos aplicados a los elementos que no están al principio de un archivo de código fuente.  
  
- **Argumentos.** Todos los argumentos posicionales de un atributo deben preceder a cualquier inicializador de variable o propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se aplica el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo a una definición de esquema de un `Function` procedimiento.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>indica que el procedimiento con atributos representa un punto de entrada de una biblioteca de vínculos dinámicos (DLL) no administrada. El atributo proporciona el nombre del archivo DLL como argumento posicional y la otra información como inicializadores de variables.  
  
## <a name="see-also"></a>Consulte también

- [Ensamblado](../modifiers/assembly.md)
- [Destina\<keyword>](../modifiers/module-keyword.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
- [Procedimiento Interrupción y combinación de instrucciones en código](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
