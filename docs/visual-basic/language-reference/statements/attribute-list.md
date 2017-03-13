---
title: "Lista de atributos (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "lista de atributos"
  - "atributos [Visual Basic], aplicar"
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Lista de atributos (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica los atributos que se van a aplicar a un elemento de programación declarado.  Los atributos múltiples se separan por comas.  A continuación, aparece la sintaxis para un atributo.  
  
## Sintaxis  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## Elementos  
 `attributemodifier`  
 Obligatorio para atributos aplicados al principio de un archivo de código fuente.  Puede ser [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) o [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Obligatorio.  Nombre del atributo.  
  
 `attributearguments`  
 Opcional.  Lista de argumentos por posición de este atributo.  Los argumentos múltiples se separan por comas.  
  
 `attributeinitializer`  
 Opcional.  Lista de inicializadores de variables o propiedades de este atributo.  Los inicializadores múltiples se separan por comas.  
  
## Comentarios  
 Puede aplicar uno o más atributos a casi cualquier elemento de programación \(tipos, procedimientos, propiedades, etc.\).  Los atributos aparecen en los metadatos del ensamblado y sirven de ayuda para anotar el código o especificar cómo se utiliza un elemento de programación determinado.  Puede aplicar atributos definidos por Visual Basic y .NET Framework, así como definir sus propios atributos.  
  
 Para obtener más información sobre cuándo se utilizan atributos, vea [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  Para obtener más información sobre nombres de atributo, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Reglas  
  
-   **Colocación.** Puede aplicar atributos a la mayoría de elementos de programación declarados.  Para aplicar uno o más atributos, coloque un *bloque de atributos* al principio de la declaración del elemento.  Cada entrada de la lista de atributos especifica un atributo que desea aplicar, y el modificador y argumentos que está utilizando para esta invocación del atributo.  
  
-   **Corchetes angulares.** Si proporciona una lista de atributos, debe incluirla entre corchetes angulares \("`<`" y "`>`"\).  
  
-   **Parte de la declaración.** El atributo debe formar la parte de la declaración del elemento y no una instrucción independiente.  Puede utilizar la secuencia de continuación de línea \(" `_`"\) para extender la instrucción de declaración a varias líneas del código fuente.  
  
-   **Modificadores.** Es obligatorio utilizar un modificador de atributo \(`Assembly` o `Module`\) en cada atributo aplicado a un elemento de programación al principio de un archivo de código fuente.  No se permiten modificadores de atributo en atributos aplicados a elementos que no estén al principio de un archivo de código fuente.  
  
-   **Argumentos.** Todos los argumentos posicionales para un atributo deben preceder a cualquier inicializador de variable o de propiedad.  
  
## Ejemplo  
 En el ejemplo siguiente se aplica el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> al esquema de una definición de un procedimiento `Function`.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> indica que el procedimiento con atributos representa un punto de entrada en una biblioteca de vínculos dinámicos no administrada \(archivo DLL\).  El atributo proporciona el nombre del archivo DLL como argumento posicional y el resto de la información como inicializadores de variable.  
  
## Vea también  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Module \<palabra clave\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)