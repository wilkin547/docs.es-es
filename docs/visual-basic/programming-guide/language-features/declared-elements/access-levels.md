---
title: "Niveles de acceso en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "niveles de acceso"
  - "niveles de acceso, elementos declarados"
  - "modificadores de acceso"
  - "elementos declarados, nivel de acceso"
  - "Friend (modificador de acceso)"
  - "miembros, obtener acceso en Visual Basic"
  - "Private (modificador de acceso)"
  - "Protected (modificador de acceso)"
  - "Protected Friend (modificador de acceso)"
  - "Public (modificador de acceso)"
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Niveles de acceso en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El *nivel de acceso* de un elemento declarado es la extensión de la capacidad de acceso a él; es decir, qué código tiene permiso para leer o escribir en él.  Está determinado no solamente por cómo se declara el propio elemento, sino también por la nivel de acceso del contenedor del elemento.  El código que no puede tener acceso a un elemento contenedor no puede tener acceso a ninguno de sus elementos contenedores, incluso aquéllos declarados como `Public`.  Por ejemplo, se puede tener acceso a una variable `Public` de una estructura `Private` desde dentro de la clase que contiene la estructura, pero no desde fuera.  
  
## Public  
 La palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md) de la instrucción de declaración especifica que se puede tener acceso a los elementos desde el código en cualquier parte del mismo proyecto, desde otros proyectos que hagan referencia al proyecto y desde un ensamblado compilado a partir del proyecto.  El código siguiente muestra un ejemplo de declaración `Public`.  
  
```  
Public Class classForEverybody  
```  
  
 Puede utilizar `Public` solamente en el nivel de módulo, interfaz o espacio de nombres.  Es decir, puede declarar un elemento público en el nivel de archivo de código fuente o espacio de nombres o dentro de una interfaz, módulo, clase o estructura, pero no dentro de un procedimiento.  
  
## Protected  
 La palabra clave [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) de la instrucción de declaración especifica que sólo se puede tener acceso a los elementos desde dentro de la misma clase o desde una clase derivada de ella.  El código siguiente muestra un ejemplo de declaración `Protected`.  
  
```  
Protected Class classForMyHeirs  
```  
  
 Sólo puede usar `Protected` en el nivel de clase y sólo al declarar un miembro de una clase.  Es decir, puede declarar un elemento protegido en una clase, pero no en el nivel de archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## Friend  
 La palabra clave [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) en la instrucción de declaración especifica que se puede tener acceso a los elementos desde dentro del mismo ensamblado, pero no desde fuera del ensamblado.  El código siguiente muestra un ejemplo de declaración `Friend`.  
  
```  
Friend stringForThisProject As String  
```  
  
 Puede utilizar `Friend` solamente en el nivel de módulo, interfaz o espacio de nombres.  Es decir, puede declarar un elemento Friend en el nivel de archivo de código fuente o espacio de nombres o dentro de una interfaz, módulo, clase o estructura, pero no dentro de un procedimiento.  
  
## Protected Friend  
 Las palabras clave `Protected` y `Friend` juntas en la instrucción de declaración especifican que se puede tener acceso a los elementos desde las clases derivadas, desde dentro del mismo ensamblado o ambos.  El código siguiente muestra un ejemplo de declaración `Protected` `Friend`.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 Sólo puede usar `Friend` `Protected` en el nivel de clase y sólo al declarar un miembro de una clase.  Es decir, puede declarar un elemento de tipo Protected Friend en una clase, pero no en el nivel de archivo de código fuente o espacio de nombres, o dentro de una interfaz, módulo, estructura o procedimiento.  
  
## Private  
 La palabra clave [Private](../../../../visual-basic/language-reference/modifiers/private.md) de la instrucción de declaración especifica que sólo se puede tener acceso a los elementos desde dentro del mismo módulo, clase o estructura.  El código siguiente muestra un ejemplo de declaración `Private`.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 Sólo puede utilizar `Private` en el nivel de módulo.  Es decir, puede declarar un elemento privado dentro de un módulo, clase o estructura, pero no en el nivel de archivo de código fuente o espacio de nombres, dentro de una interfaz o un procedimiento.  
  
 En el nivel de módulo, la instrucción `Dim` sin ninguna palabra clave de nivel de acceso es equivalente a una declaración `Private`.  No obstante, podría convenirle usar la palabra clave `Private` para facilitar la lectura y la interpretación del código.  
  
## Modificadores de acceso  
 Las palabras clave que especifican el nivel de acceso se llaman *modificadores de acceso*.  La tabla siguiente compara los modificadores de acceso.  
  
|Modificador de acceso|Nivel de acceso concedido|Elementos que puede declarar con este nivel de acceso|Contexto de declaración dentro de cual puede utilizar este modificador|  
|---------------------------|-------------------------------|-----------------------------------------------------------|----------------------------------------------------------------------------|  
|`Public`|Sin restricciones:<br /><br /> Cualquier código que puede ver un elemento público puede tener acceso a él.|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables miembros<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Módulo<br /><br /> Clase<br /><br /> Estructura|  
|`Protected`|De derivación:<br /><br /> El código de la clase que declara un elemento protegido, o una clase derivada de él, puede tener acceso al elemento.|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables miembros<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Friend`|Ensamblado:<br /><br /> El código del ensamblado que declara un elemento de tipo Friend puede tener acceso a él.|Interfaces<br /><br /> Módulos<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables miembros<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Archivo de código fuente<br /><br /> Espacio de nombres<br /><br /> Interfaz<br /><br /> Módulo<br /><br /> Clase<br /><br /> Estructura|  
|`Protected` `Friend`|Unión de `Protected` y `Friend`:<br /><br /> El código de la misma clase o el mismo ensamblado que el elemento de tipo Protected Friend o aquel que está dentro de cualquier clase derivada de la clase del elemento, puede tener acceso a él.|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables miembros<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Clase|  
|`Private`|Contexto de declaración:<br /><br /> El código del tipo que declara un elemento privado, incluido el código de los tipos contenidos, puede tener acceso al elemento.|Interfaces<br /><br /> Clases<br /><br /> Estructuras<br /><br /> Miembros de estructura<br /><br /> Procedimientos<br /><br /> Propiedades<br /><br /> Variables miembros<br /><br /> Constantes<br /><br /> Enumeraciones<br /><br /> Eventos<br /><br /> Declaraciones externas<br /><br /> Delegados|Módulo<br /><br /> Clase<br /><br /> Estructura|  
  
## Vea también  
 [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Cómo: Controlar la disponibilidad de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)