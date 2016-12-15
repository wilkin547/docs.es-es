---
title: "Diferencias entre propiedades y variables en Visual Basic | Microsoft Docs"
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
  - "propiedades [Visual Basic], y variables"
  - "propiedades [Visual Basic], definición"
  - "propiedades [Visual Basic], valores"
  - "valores de propiedades"
  - "valores, propiedades"
  - "variables [Visual Basic]"
  - "variables [Visual Basic], y propiedades"
  - "variables [Visual Basic], definición"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
  - "código de Visual Basic, variables"
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Diferencias entre propiedades y variables en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Tanto las variables como las propiedades representan valores a los que puede tener acceso.  Sin embargo, existen diferencias en su almacenamiento e implementación.  
  
## Variables  
 Una *variable* se corresponde directamente con una ubicación de la memoria.  Una variable se define con una única instrucción de declaración.  Una variable puede ser una *variable local*, si está definida dentro de un procedimiento y sólo está disponible en dicho procedimiento, o puede ser una *variable miembro*, si se define en un módulo, una clase o una estructura, pero no dentro de un procedimiento.  Una variable miembro también se denomina *campo*.  
  
## Propiedades  
 Una *propiedad* es un elemento de datos que se define en un módulo, una clase o una estructura.  Una propiedad se define con un bloque de código comprendido entre las instrucciones `Property` y `End Property`.  El bloque de código contiene un procedimiento `Get`, un procedimiento `Set` o ambos procedimientos.  Estos procedimientos se denominan *procedimientos de propiedades* o *descriptores de acceso de propiedades*.  Además de recuperar o almacenar el valor de una propiedad, también pueden llevar a cabo acciones personalizadas, como actualizar un contador de acceso.  
  
## Diferencias  
 En la tabla siguiente se muestran algunas diferencias importantes que existen entre las variables y propiedades.  
  
|Punto de diferencia|Variable|Propiedad.|  
|-------------------------|--------------|----------------|  
|Declaración|Única instrucción de declaración|Serie de instrucciones en un bloque de código|  
|Implementación|Única ubicación de almacenamiento|Código ejecutable \(procedimientos de propiedades\)|  
|Almacenamiento|Directamente asociado con el valor de una variable|Normalmente dispone de un almacén interno que no está disponible fuera de la clase o el módulo que contiene la propiedad<br /><br /> El valor de la propiedad podría existir o no como un elemento almacenado <sup>1</sup>|  
|Código ejecutable|None|Debe tener al menos un procedimiento|  
|Acceso de lectura y escritura|Acceso de lectura y escritura o de sólo lectura|Acceso de lectura y escritura, de sólo lectura o de sólo escritura|  
|Acciones personalizadas \(además de aceptar o devolver un valor\)|No es posible|Se pueden llevar a cabo como parte del proceso de configuración o de recuperación del valor de propiedad|  
  
 <sup>1</sup> A diferencia de una variable, es posible que el valor de una propiedad no se corresponda directamente con un único elemento de almacenamiento.  El almacenamiento podría dividirse en partes por motivos de comodidad o seguridad, o el valor podría almacenarse en un formato cifrado.  En estos casos, el procedimiento `Get` ensamblaría las partes o descifraría el valor almacenado, y el procedimiento `Set` cifraría el nuevo valor o lo dividiría en el almacenamiento fundamental.  El valor de una propiedad podría ser efímero, como una hora del día, en cuyo caso el procedimiento `Get` lo calcularía sobre la marcha cada vez que se obtuviera acceso a la propiedad.  
  
## Vea también  
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)