---
title: "Structure (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Structure"
  - "Structure"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos compuestos"
  - "Structure (palabra clave)"
  - "Structure (instrucción)"
  - "tipos [Visual Basic], definidas por el usuario"
  - "UDT (tipos definidos por el usuario)"
  - "tipos definidos por el usuario, Structure (instrucción)"
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Structure (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara el nombre de una estructura e introduce la definición de las variables, propiedades, eventos y procedimientos que la estructura incluye.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attributelist`|Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional.  Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Opcional.  Indica una definición parcial de la estructura.  Vea [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Requerido.  Nombre de esta estructura.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional.  Especifica que se trata de una estructura genérica.|  
|`typelist`|Es obligatorio si se utiliza la palabra clave [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Lista de parámetros de tipo de esta estructura.  Vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Opcional.  Indica que esta estructura implementa los miembros de una o más interfaces.  Vea [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`.  Nombres de las interfaces implementadas por esta estructura.|  
|`datamemberdeclarations`|Requerido.  Cero o más instrucciones `Const`, `Dim`, `Enum` o `Event` que declaran los *miembros de datos* de la estructura.|  
|`methodmemberdeclarations`|Opcional.  Cero o más declaraciones de los procedimientos `Function`, `Operator`, `Property` o `Sub` que sirven como *miembros de método* de la estructura.|  
|`End Structure`|Requerido.  Termina la definición de `Structure`.|  
  
## Comentarios  
 La instrucción `Structure` define un tipo de valor compuesto que se puede personalizar.  Una *estructura* es una generalización de un tipo definido por el usuario de versiones anteriores de Visual Basic.  Para obtener más información, vea [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Las estructuras admiten muchas de las mismas características que las clases.  Por ejemplo, las estructuras pueden tener propiedades y procedimientos, pueden implementar interfaces y pueden tener constructores con parámetros.  No obstante, existen diferencias importantes entre las estructuras y las clases en materias como la herencia, las declaraciones y la utilización.  Además, las clases son tipos de referencia y las estructuras son tipos de valor.  Para obtener más información, vea [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 `Structure` solo se puede utilizar en un espacio de nombres o un nivel de módulo.  Esto significa que el *contexto de la declaración* de una estructura debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento ni un bloque.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 De manera predeterminada, el acceso a las estructuras es de tipo [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Los niveles de acceso se pueden ajustar con los modificadores de acceso.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Reglas  
  
-   **Anidamiento.** Puede definirse una estructura dentro de otra.  La estructura exterior se denomina *estructura contenedora* y la interna *estructura anidada*.  Sin embargo, no se puede tener acceso a los miembros de una estructura anidada a través de la estructura contenedora.  En lugar de ello, se debe declarar una variable del tipo de datos de la estructura anidada.  
  
-   **Declaración de miembros.** Se debe declarar cada miembro de una estructura.  Los miembros de una estructura no pueden ser de tipo [Protected](../../../visual-basic/language-reference/modifiers/protected.md) ni `Protected Friend` ya que no se puede heredar nada de una estructura.  La propia estructura, sin embargo, puede ser de tipo `Protected` o `Protected Friend`.  
  
     En una estructura se pueden declarar cero o más variables no compartidas o eventos no compartidos y no personalizados.  No pueden utilizarse únicamente constantes, propiedades y procedimientos, aunque algunos sean no compartidos.  
  
-   **Inicialización.** No se puede inicializar el valor de ningún miembro de datos de una estructura no compartido como parte de su declaración.  Dicho miembro de datos se debe inicializar mediante un constructor con parámetros en la estructura o bien mediante la asignación de un valor al miembro después de crear una instancia de la estructura.  
  
-   **Herencia.** Una estructura no puede heredar de ningún tipo distinto de <xref:System.ValueType>, del que todas las estructuras heredan.  En particular, una estructura no puede heredar de otra.  
  
     [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md) no se puede utilizar en una definición de estructura, ni siquiera para especificar <xref:System.ValueType>.  
  
-   **Implementación.** Si la estructura utiliza [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md), se debe implementar cada miembro definido por cada interfaz que se especifica en `interfacenames`.  
  
-   **Propiedad Default.** Una estructura puede especificar a lo sumo una propiedad como su *propiedad predeterminada*, mediante el modificador [Default](../../../visual-basic/language-reference/modifiers/default.md).  Para obtener más información, vea [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Comportamiento  
  
-   **Nivel de acceso.** En una estructura, cada miembro se puede declarar con su propio nivel de acceso.  El acceso predeterminado de todos los miembros de la estructura es de tipo [Public](../../../visual-basic/language-reference/modifiers/public.md).  Tenga en cuenta que si la propia estructura utiliza un nivel de acceso más limitado, se restringe automáticamente el acceso a sus miembros, aunque los niveles de acceso se ajusten con modificadores.  
  
-   **Ámbito.** Una estructura está en ámbito en su espacio de nombres, clase, estructura o módulo contenedores.  
  
     El ámbito de todos los miembros de la estructura es la estructura completa.  
  
-   **Duración.** Una estructura no dispone por sí misma de período de duración.  Más bien, cada instancia de esa estructura tiene un período de duración independiente de todas las demás instancias.  
  
     El período de duración de una instancia comienza cuando se crea con una cláusula [New \(Operador\)](../../../visual-basic/language-reference/operators/new-operator.md).  Finaliza cuando finaliza el período de duración de la variable que la contiene.  
  
     No puede extender el período de duración de una instancia de estructura.  Los módulos proporcionan una aproximación a la funcionalidad de estructura estática.  Para obtener más información, vea [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de estructura disponen de un período de duración en función de cómo y donde se declaran.  Para obtener más información, vea el apartado sobre períodos de duración en [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Calificación.** El código que se incluye fuera de una estructura debe calificar el nombre de un miembro con el nombre de dicha estructura.  
  
     Si el código incluido en una estructura anidada realiza una referencia sin calificar a un elemento de programación, Visual Basic busca este elemento en la estructura anidada en primer lugar, a continuación en la estructura contenedora y así sucesivamente hasta el elemento contenedor principal.  Para obtener más información, vea [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros.  Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración.  Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza la instrucción `Structure` para definir un conjunto de datos relacionados de un empleado.  Se muestra el uso de los miembros `Public`, `Friend` y `Private` para reflejar la confidencialidad de los elementos de datos.  También se muestran los miembros de evento, propiedad y procedimiento.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## Vea también  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)