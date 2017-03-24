---
title: Atributo lista (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e360794ad217784e2358967bfbcc03959cd043b1
ms.lasthandoff: 03/13/2017

---
# <a name="attribute-list-visual-basic"></a>Lista de atributos (Visual Basic)
Especifica los atributos que se aplicará a un elemento de programación declarado. Los diversos atributos se separan con comas. A continuación se muestra la sintaxis para un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Elementos  
 `attributemodifier`  
 Obligatorio para atributos aplicados al principio de un archivo de origen. Puede ser [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) o [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Obligatorio. Nombre del atributo.  
  
 `attributearguments`  
 Opcional. Lista de argumentos posicionales para este atributo. Varios argumentos están separados por comas.  
  
 `attributeinitializer`  
 Opcional. Lista de inicializadores de variable o propiedad para este atributo. Inicializadores múltiples se separan por comas.  
  
## <a name="remarks"></a>Comentarios  
 Puede aplicar uno o más atributos a casi cualquier elemento de programación (tipos, procedimientos, propiedades etc.). Los atributos aparecen en los metadatos del ensamblado y sirven de ayuda para anotar el código o especificar cómo se utiliza un elemento de programación determinado. Puede aplicar atributos definidos por Visual Basic y .NET Framework, y puede definir sus propios atributos.  

 Para obtener más información sobre cuándo utilizar los atributos, vea [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md). Para obtener información sobre nombres de atributo, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Selección de ubicación.** Puede aplicar atributos a elementos de programación declarados más. Para aplicar uno o varios atributos, se coloca un *bloque de atributos* al principio de la declaración del elemento. Cada entrada de la lista de atributos especifica un atributo que se va a aplicar, y el modificador y argumentos que está utilizando para esta invocación del atributo.  
  
-   **Corchetes angulares.** Si se proporciona una lista de atributos, lo debe encerrar entre corchetes angulares ("`<`"y"`>`").  
  
-   **Parte de la declaración.** El atributo debe ser parte de la declaración de elemento, no una instrucción independiente. Puede utilizar la secuencia de continuación de línea (" `_`") para extender la instrucción de declaración a varias líneas de código fuente.  
  
-   **Modificadores.** Un modificador de atributo (`Assembly` o `Module`) es necesario en cada atributo aplicado a un elemento de programación al principio de un archivo de origen. No se permiten modificadores de atributo en atributos aplicados a elementos que no están al principio de un archivo de origen.  
  
-   **Argumentos.** Todos los argumentos posicionales para un atributo deben preceder a cualquier inicializador de variable o propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente aplica el <xref:System.Runtime.InteropServices.DllImportAttribute>atributo a un esquema de definición de un `Function` procedimiento.</xref:System.Runtime.InteropServices.DllImportAttribute>  
  
 [!code-vb[1 VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>indica que el procedimiento con atributos representa un punto de entrada en una biblioteca de vínculos dinámicos (DLL) no administrada.</xref:System.Runtime.InteropServices.DllImportAttribute> El atributo proporciona el nombre del archivo DLL como un argumento posicional y el resto de información como inicializadores de variables.  
  
## <a name="see-also"></a>Vea también  
 [Ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Módulo \<palabra clave >](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
