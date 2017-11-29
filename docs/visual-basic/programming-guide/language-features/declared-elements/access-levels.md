---
title: Niveles de acceso en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87e43ac7e813cece1179bdaf24c86fa62adcb438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-levels-in-visual-basic"></a>Niveles de acceso en Visual Basic
El *nivel de acceso* de un elemento declarado es la extensión de la capacidad de tener acceso a ella, es decir, qué código tiene permiso para leer o escribir en él. Esto se determina no solo por cómo se declara el propio elemento, sino también por el nivel de acceso del contenedor del elemento. Código que no se puede obtener acceso a un elemento contenedor no puede tener acceso a cualquiera de los elementos contenidos, aunque se hayan declarado como `Public`. Por ejemplo, un `Public` variable en un `Private` estructura puede tener acceso desde dentro de la clase que contiene la estructura, pero no desde fuera de esa clase.  
  
## <a name="public"></a>Público  
 El [público](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave de la instrucción de declaración especifica que se pueden tener acceso a los elementos desde el código en cualquier lugar en el mismo proyecto, desde otros proyectos que hagan referencia al proyecto y de cualquier ensamblado compilado a partir del proyecto. El código siguiente muestra un ejemplo `Public` declaración.  
  
```  
Public Class classForEverybody  
```  
  
 Puede usar `Public` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que puede declarar un elemento público en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, clase o estructura, pero no en un procedimiento.  
  
## <a name="protected"></a>Protegido  
 El [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) palabra clave de la instrucción de declaración especifica que los elementos son accesibles únicamente desde dentro de la misma clase o de una clase derivada de esta clase. El código siguiente muestra un ejemplo `Protected` declaración.  
  
```  
Protected Class classForMyHeirs  
```  
  
 Puede usar `Protected` solo en la clase de nivel y solo cuando se declara un miembro de una clase. Esto significa que puede declarar un elemento protegido en una clase, pero no en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## <a name="friend"></a>Friend  
 El [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) palabra clave de la instrucción de declaración especifica que los elementos son accesibles desde dentro del mismo ensamblado, pero no desde fuera del ensamblado. El código siguiente muestra un ejemplo `Friend` declaración.  
  
```  
Friend stringForThisProject As String  
```  
  
 Puede usar `Friend` sólo en el nivel de módulo, interfaz o espacio de nombres. Esto significa que puede declarar un elemento friend en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, clase o estructura, pero no en un procedimiento.  
  
## <a name="protected-friend"></a>Protected Friend  
 El `Protected` y `Friend` palabras clave en la instrucción de declaración especifica que se pueden tener acceso a los elementos desde las clases derivadas o desde dentro del mismo ensamblado o ambos. El código siguiente muestra un ejemplo `Protected Friend` declaración.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Puede usar `Protected Friend` solo en la clase de nivel y solo cuando se declara un miembro de una clase. Esto significa que puede declarar un elemento friend protegido en una clase, pero no en el nivel de un archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## <a name="private"></a>Private  
 El [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave de la instrucción de declaración especifica que los elementos son accesibles únicamente desde dentro del mismo módulo, clase o estructura. El código siguiente muestra un ejemplo `Private` declaración.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 Solo se puede usar `Private` en un nivel de módulo. Esto significa que se puede declarar un elemento privado dentro de un módulo, clase o estructura, pero no en el nivel de un archivo de código fuente o espacio de nombres, dentro de una interfaz o en un procedimiento.  
  
 En el nivel de módulo, el `Dim` instrucción sin las palabras clave de nivel de acceso es equivalente a un `Private` declaración. Sin embargo, puede usar el `Private` palabra clave que el código sea más fácil de leer e interpretar.  
  
## <a name="access-modifiers"></a>Modificadores de acceso  
 Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*. En la tabla siguiente compara los modificadores de acceso.  
  
|Modificador de acceso|Nivel de acceso concedido|Los elementos se pueden declarar con este nivel de acceso|Contexto de la declaración dentro del cual se puede utilizar este modificador|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Sin restricciones:<br /><br /> Cualquier código que puede ver un elemento público puede obtener acceso a él|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Módulo<br /><br /> Clase<br /><br /> Estructura|  
|`Protected`|Por ejemplo:<br /><br /> En la clase que declara un elemento protegido o una clase derivada de ella, puede tener acceso al elemento de código|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Friend`|Ensamblado:<br /><br /> Código del ensamblado que declara un elemento friend puede tener acceso a él|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Módulo<br /><br /> Clase<br /><br /> Estructura|  
|`Protected` `Friend`|Unión de `Protected` y `Friend`:<br /><br /> En la misma clase o el mismo ensamblado como un elemento de tipo amigo protegido o dentro de cualquier clase que deriva de la clase del elemento de código, puede obtener acceso a él|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Private`|Contexto de la declaración:<br /><br /> Código en el tipo que declara un elemento privado, incluido el código de los tipos contenidos, puede tener acceso al elemento|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables de miembro<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Módulo<br /><br /> Clase<br /><br /> Estructura|  
  
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
