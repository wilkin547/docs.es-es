---
title: "Property (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
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
ms.openlocfilehash: 87cb32c12ab3238508a6a4bb114306909e409dda
ms.lasthandoff: 03/13/2017

---
# <a name="property-statement"></a>Property Statement
Declara el nombre de una propiedad y los procedimientos de propiedad utilizados para almacenar y recuperar el valor de la propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
  
```  
  
## <a name="parts"></a>Elementos  
  
-   `attributelist`  
  
     Opcional. Lista de atributos que se aplican a esta propiedad o `Get` o `Set` procedimiento. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Opcional. Especifica que esta propiedad es la propiedad predeterminada de la clase o estructura en el que se define. Propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de propiedad. Si se declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.  
  
-   `accessmodifier`  
  
     Opcional en la `Property` instrucción y en al menos uno de los `Get` y `Set` instrucciones. Puede ser uno de los siguientes:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Consulte [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Opcional. Consulte [compartido](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Opcional. Consulte [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Opcional. Consulte [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Opcional. Consulte [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Obligatorio. Nombre de la propiedad. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Opcional. Lista de nombres de variables locales que representan los parámetros de esta propiedad y posibles parámetros adicionales de la `Set` procedimiento. Consulte [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Requerido si `Option``Strict` es `On`. Tipo de datos del valor devuelto por esta propiedad.  
  
-   `Implements`  
  
     Opcional. Indica que esta propiedad implementa una o más propiedades, cada uno definido en una interfaz implementada por la clase o estructura contenedora de esta propiedad. Consulte [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Es necesario si se proporciona `Implements`. Lista de propiedades que se implementan.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Cada `implementedproperty` tiene la sintaxis y las partes siguientes:  
  
     `interface.definedname`  
  
    |Parte|Descripción|  
    |---|---|  
    |`interface`|Obligatorio. Nombre de una interfaz implementada por esta propiedad contenedora de clase o estructura.|  
    |`definedname`|Obligatorio. Nombre por el que se define la propiedad en `interface`.|  
  
-   `Get`  
  
     Opcional. Requerido si se marca la propiedad `WriteOnly`. Inicia un `Get` procedimiento de propiedad que se utiliza para devolver el valor de la propiedad.  
  
-   `statements`  
  
     Opcional. Bloque de instrucciones que se ejecutan dentro de la `Get` o `Set` procedimiento.  
  
-   `End Get`  
  
     Finaliza el `Get` el procedimiento de propiedad.  
  
-   `Set`  
  
     Opcional. Requerido si se marca la propiedad `ReadOnly`. Inicia un `Set` procedimiento de propiedad que se utiliza para almacenar el valor de la propiedad.  
  
-   `End Set`  
  
     Finaliza el `Set` el procedimiento de propiedad.  
  
-   `End Property`  
  
     Termina la definición de esta propiedad.  
  
## <a name="remarks"></a>Comentarios  
 El `Property` instrucción presenta la declaración de una propiedad. Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (sólo escritura) o ambas (de lectura y escritura). Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente. Para obtener más información, consulte [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Puede usar `Property` sólo en el nivel de clase. Esto significa que la *contexto de la declaración* de una propiedad debe ser una clase, estructura, módulo o interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento ni un bloque. Para obtener más información, consulte [contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 De forma predeterminada, propiedades utilizan acceso público. Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la `Property` instrucción y, opcionalmente, ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.  
  
 Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad. Si no se especifica un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`. Este parámetro contiene el valor que se asignará a la propiedad. Normalmente almacenar este valor en una variable local privada y lo devuelve cada vez que la `Get` se llama al procedimiento.  
  
## <a name="rules"></a>Reglas  
  
-   **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend`, puede declarar la `Set` procedimiento `Private`, pero no `Public`.  
  
     Si va a definir un `ReadOnly` o `WriteOnly` propiedad, el procedimiento de propiedad único (`Get` o `Set`, respectivamente) representa toda la propiedad. No se puede declarar un nivel de acceso diferente para este procedimiento, porque se establecerían dos niveles de acceso para la propiedad.  
  
-   **Tipo de valor devuelto.** El `Property` instrucción puede declarar el tipo de datos del valor que se devuelve. Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.  
  
     Si no se especifica `returntype`, la propiedad devuelve `Object`.  
  
-   **Implementación.** Si utiliza esta propiedad el `Implements` (palabra clave), la clase o estructura contenedora debe tener un `Implements` instrucción inmediatamente siguiente a su `Class` o `Structure` instrucción. El `Implements` instrucción debe incluir cada interfaz especificada en `implementslist`. Sin embargo, el nombre por el que una interfaz define la `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Devolver desde un procedimiento de propiedad.** Cuando el `Get` o `Set` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.  
  
     El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier parte en el procedimiento y puede combinar `Exit Property` y `Return` instrucciones.  
  
-   **Valor devuelto.** Para devolver un valor desde una `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en una `Return` instrucción. En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, usa el `Exit Property` instrucción para devolver.  
  
     [!code-vb[VbVbalrStatements Nº&27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     Si utiliza `Exit Property` sin asignar un valor a `name`, el `Get` procedimiento devuelve el valor predeterminado tipo de la propiedad de datos.  
  
     El `Return` instrucción al mismo tiempo asigna el `Get` procedimiento devuelve el valor y sale del procedimiento. En el ejemplo siguiente se muestra cómo hacerlo.  
  
     [!code-vb[VbVbalrStatements Nº&27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una propiedad en una clase.  
  
 [!code-vb[VbVbalrStatements&#51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Propiedades autoimplementadas](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Predetermiado](../../../visual-basic/language-reference/modifiers/default.md)
