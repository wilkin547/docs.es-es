---
title: "Clases COM de ejemplo (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "COM, exponer objetos de Visual C# en"
  - "ejemplos [C#], clases COM"
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Clases COM de ejemplo (Gu&#237;a de programaci&#243;n de C#)
A continuación se incluye un ejemplo de una clase que se expondría como un objeto COM.  Una vez insertado este código de ejemplo en un archivo .cs y agregado al proyecto, establezca la propiedad **Registrar para interoperabilidad COM** en **True**.  Para obtener más información, vea [NIB: How to: Register a Component for COM Interop](http://msdn.microsoft.com/es-es/4de7d474-56e8-4027-994d-d47ca4725c5e).  
  
 Exponer objetos de Visual C\# para COM requiere declarar una interfaz de clase, una interfaz de eventos si es necesario y la propia clase.  Los miembros de clase deben seguir estas reglas para que sean visibles en COM:  
  
-   La clase debe ser pública.  
  
-   Las propiedades, métodos y eventos deben ser públicos.  
  
-   Las propiedades y métodos deben declararse en la interfaz de clase.  
  
-   Los eventos deben declararse en la interfaz de eventos.  
  
 Los demás miembros públicos de la clase que no se hayan declarado en estas interfaces no serán visibles para COM, pero lo serán para el resto de objetos de .NET Framework.  
  
 Para exponer propiedades y métodos en COM, se deben declarar en la interfaz de clase y marcarlos con el atributo `DispId`, e implementarlos en la clase.  El orden en que se declaran los miembros en la interfaz es el orden utilizado para la tabla vtable COM.  
  
 Para poder exponer los eventos de una clase, se deben declarar en la interfaz de eventos y marcarlos con un atributo `DispId`.  La clase no debe implementar esta interfaz.  
  
 La clase implementa la interfaz de clase; puede implementar más de una interfaz, pero la primera implementación debe ser la interfaz de clase predeterminada.  Implemente los métodos y propiedades expuestos para COM aquí.  Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de clase.  Asimismo, declare los eventos que inicia la clase aquí.  Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de eventos.  
  
## Ejemplo  
 [!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/csharp/example-com-class_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Interoperabilidad](../../../csharp/programming-guide/interop/interoperability.md)   
 [Compilar \(Página, Diseñador de proyectos\) \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)