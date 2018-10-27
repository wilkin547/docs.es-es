---
title: Niveles de acceso en Visual Basic
ms.date: 05/10/2018
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private Protected access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 433d5dfd4bb3af9b6fbd0dfc951bb0448eb7efcd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183150"
---
# <a name="access-levels-in-visual-basic"></a>Niveles de acceso en Visual Basic
El *nivel de acceso* de un elemento declarado es la extensión de la capacidad de obtener acceso a él, es decir, qué código tiene permiso para leer o escribir en él. Esto se determina no solo por cómo se declara el propio elemento, sino también por el nivel de acceso del contenedor del elemento. Código que no se puede obtener acceso a un elemento contenedor no puede tener acceso a cualquiera de los elementos contenidos, aunque se hayan declarado como `Public`. Por ejemplo, un `Public` variable en un `Private` estructura se puede acceder desde dentro de la clase que contiene la estructura, pero no desde fuera de esa clase.  
  
## <a name="public"></a>Public  
 El [pública](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave de la instrucción de declaración especifica que el elemento se puede acceder desde el código en cualquier lugar en el mismo proyecto, desde otros proyectos que hagan referencia al proyecto y de cualquier ensamblado compilado a partir del proyecto. El código siguiente muestra un ejemplo `Public` declaración.  
  
```vb  
Public Class classForEverybody  
```  
  
 Puede usar `Public` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que puede declarar un elemento público en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, clase o estructura, pero no en un procedimiento.  
  
## <a name="protected"></a>Protegido  
 El [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) palabra clave de la instrucción de declaración especifica que el elemento se puede acceder solo desde dentro de la misma clase, o desde una clase derivada de esta clase. El código siguiente muestra un ejemplo `Protected` declaración.  
  
```vb  
Protected Class classForMyHeirs  
```  
  
 Puede usar `Protected` solo en la clase de nivel y solo cuando se declara un miembro de una clase. Esto significa que puede declarar un elemento protegido en una clase, pero no en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## <a name="friend"></a>Friend  
 El [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) palabra clave de la instrucción de declaración especifica que el elemento se puede acceder desde dentro del mismo ensamblado, pero no desde fuera del ensamblado. El código siguiente muestra un ejemplo `Friend` declaración.  
  
```vb  
Friend stringForThisProject As String  
```  
  
 Puede usar `Friend` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que puede declarar un elemento friend en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, clase o estructura, pero no en un procedimiento.  
  
## <a name="protected-friend"></a>Protected Friend  
 El [Protected Friend](../../../language-reference/modifiers/protected-friend.md) combinación de palabras clave en la instrucción de declaración especifica que el elemento se puede acceder desde las clases derivadas o desde dentro del mismo ensamblado, o ambos. El código siguiente muestra un ejemplo `Protected Friend` declaración.  
  
```vb  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Puede usar `Protected Friend` solo en la clase de nivel y solo cuando se declara un miembro de una clase. Esto significa que puede declarar un elemento friend protegido en una clase, pero no en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## <a name="private"></a>Private  
 El [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave de la instrucción de declaración especifica que el elemento se puede acceder solo desde dentro del mismo módulo, clase o estructura. El código siguiente muestra un ejemplo `Private` declaración.  
  
```vb  
Private numberForMeOnly As Integer  
```  
  
 Solo se puede usar `Private` en un nivel de módulo. Esto significa que puede declarar un elemento privado dentro de un módulo, clase o estructura, pero no en el nivel de un archivo de código fuente o espacio de nombres dentro de una interfaz o en un procedimiento.  
  
 En el nivel de módulo, el `Dim` instrucción sin las palabras clave de nivel de acceso es equivalente a un `Private` declaración. Sin embargo, puede usar el `Private` palabra clave para que el código sea más fácil de leer e interpretar.  

## <a name="private-protected"></a>Private protegida

El [Private Protected](../../../language-reference/modifiers/private-protected.md) combinación de palabras clave en la instrucción de declaración especifica que el elemento se puede acceder solo desde dentro de la misma clase, así como de las clases derivadas que se encuentra en el mismo ensamblado que la clase contenedora. El `Private Protected` modificador de acceso se admite a partir de Visual Basic 15.5.

El ejemplo siguiente se muestra un `Private Protected` declaración:

```vb
Private Protected internalValue As Integer
```

Puede declarar un `Private Protected` elemento solo dentro de una clase. No puede declarar dentro de una interfaz o estructura, ni puede declararla en el nivel de un archivo de código fuente o espacio de nombres dentro de una interfaz o una estructura o en un procedimiento.

El `Private Protected` modificador de acceso es compatible con Visual Basic 15.5 y versiones posteriores. Para ello, agregue el siguiente elemento al archivo de proyecto (*.vbproj) de Visual Basic. Siempre que Visual Basic 15.5 o posterior esté instalado en el sistema, le permite aprovechar todas las características del lenguaje compatible con la versión más reciente del compilador de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Para usar el `Private Protected` modificador de acceso, debe agregar el elemento siguiente al archivo de proyecto (*.vbproj) de Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Para obtener más información, consulte [configuración de la versión de idioma de Visual Basic](../../../language-reference/configure-language-version.md).

 ## <a name="access-modifiers"></a>Modificadores de acceso  
 Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*. En la tabla siguiente compara los modificadores de acceso.  
  
|Modificador de acceso|Nivel de acceso concedido|Elementos que puede declarar con este nivel de acceso|Contexto de declaración dentro del cual se puede usar este modificador|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Sin restricciones:<br /><br /> Cualquier código que puede ver un elemento público puede tener acceso a él|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Module<br /><br /> Clase<br /><br /> Estructura|  
|`Protected`|Por ejemplo:<br /><br /> En la clase que declara un elemento protegido o una clase derivada de él, puede tener acceso al elemento de código|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Friend`|Ensamblado:<br /><br /> En el ensamblado que declara que un elemento friend puede tener acceso de código|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Module<br /><br /> Clase<br /><br /> Estructura|  
|`Protected` `Friend`|Unión de `Protected` y `Friend`:<br /><br /> En la misma clase o el mismo ensamblado como un elemento friend protegido o dentro de cualquier clase derivada de la clase del elemento de código, puede acceder a él|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Private`|Contexto de declaración:<br /><br /> Código en el tipo que declara un elemento privado, incluido el código de los tipos contenidos, puede tener acceso al elemento|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Module<br /><br /> Clase<br /><br /> Estructura|
|`Private Protected`|En la clase que declara un elemento privado protegido, o código en una clase derivada, que se encuentra en el mismo ensamblado que la clase de bas.|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Controlar la disponibilidad de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
