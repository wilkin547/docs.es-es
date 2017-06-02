---
title: "Clase Exception y propiedades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Exception (clase)"
  - "excepciones, Exception (clase)"
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Clase Exception y propiedades
La clase <xref:System.Exception> es la clase base de la que derivan las excepciones.  La mayoría de los objetos de excepción son instancias de alguna clase derivada de **Exception**, pero se puede producir cualquier objeto derivado de la clase <xref:System.Object> como excepción.  Tenga en cuenta que no todos los lenguajes admiten que se produzcan y detecten objetos que no se derivan de la clase **Exception**.  En casi todos los casos, es recomendable producir y detectar sólo objetos **Exception**.  
  
 La clase **Exception** tiene varias propiedades que facilitan la comprensión de una excepción.  Entre estas propiedades, se incluyen:  
  
-   Propiedad <xref:System.Exception.StackTrace%2A>  
  
     Esta propiedad contiene un seguimiento de pila que se puede utilizar para determinar dónde se ha producido un error.  El seguimiento de pila contiene el nombre del archivo de código fuente y el número de la línea del programa si está disponible la información de depuración.  
  
-   Propiedad <xref:System.Exception.InnerException%2A>  
  
     Esta propiedad se puede utilizar para crear y conservar una serie de excepciones mientras se realiza el control de excepciones.  Esta propiedad se puede usar para crear una nueva excepción que contiene excepciones detectadas con anterioridad.  La segunda excepción puede capturar la excepción original en la propiedad **InnerException**, permitiendo que el código que controla la segunda excepción examine la información adicional.  
  
     Por ejemplo, supongamos que tenemos un método que lee un archivo y da formato a los datos.  El código intenta leer en el archivo, pero se produce una FileException.  El método detecta la FileException y produce una BadFormatException.  En este caso, la FileException se puede guardar en la propiedad **InnerException** de la BadFormatException.  
  
     Para mejorar la capacidad del llamador para determinar por qué se produce una excepción, a veces es recomendable que un método detecte una excepción producida por una rutina auxiliar y, a continuación, produzca una excepción más indicativa del error que se ha producido.  Se puede crear una nueva excepción con más sentido, en que la referencia a la excepción interior se puede establecer en la excepción original.  Esta excepción, que es más significativa, puede producirse a continuación en el llamador.  Observe que con esta funcionalidad se puede crear una serie de excepciones vinculadas que termina con la excepción que se produjo en primer lugar.  
  
-   Propiedad <xref:System.Exception.Message%2A>  
  
     Esta propiedad proporciona información sobre la causa de una excepción.  El lenguaje de **Message** es el especificado por la propiedad <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName> del subproceso que inicia la excepción.  
  
-   Propiedad <xref:System.Exception.HelpLink%2A>  
  
     Esta propiedad puede tener la dirección URL \(o URN\) de un archivo de ayuda que proporciona mucha información sobre la causa de una excepción.  
  
-   La propiedad <xref:System.Exception.Data%2A>  
  
     Esta propiedad es IDictionary y puede contener datos arbitrarios en pares clave\-valor.  
  
 La mayoría de las clases derivadas de la clase **Exception** no implementan miembros adicionales ni proporcionan más funcionalidad, simplemente heredan de **Exception**.  Por ello, la información más importante sobre una excepción se encuentra en la jerarquía de excepciones, el nombre de la excepción y la información que contiene la excepción.  
  
## Vea también  
 [Jerarquía de excepciones](../../../docs/standard/exceptions/exception-hierarchy.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Procedimientos recomendados para excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Excepciones](../../../docs/standard/exceptions/index.md)