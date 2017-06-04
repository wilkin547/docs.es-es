---
title: "Creating a Class to Hold DLL Functions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, DLL functions"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "interoperation with unmanaged code, DLL functions"
  - "interoperation with unmanaged code, platform invoke"
  - "platform invoke, creating class for functions"
  - "DLL functions"
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Creating a Class to Hold DLL Functions
Empaquetar una función de un archivo DLL de una clase administrada que se utiliza con frecuencia es un buen sistema para encapsular la funcionalidad de la plataforma.  Aunque no es obligatorio hacerlo en todos los casos, es muy cómodo proporcionar un contenedor de clase porque la definición de funciones de archivos DLL puede ser una tarea laboriosa y puede dar lugar a errores.  Si está programando en C\# o Visual Basic, debe declarar las funciones de archivos DLL dentro de una clase o módulo de Visual Basic.  
  
 Dentro de una clase, se define un método estático para cada función a la que se desea llamar de un archivo DLL.  La definición puede contener información adicional, como el juego de caracteres o la convención de llamada utilizada para pasar argumentos de método; si se omite esta información, se seleccionan los valores predeterminados.  Para obtener una lista completa de las opciones de declaración y sus valores predeterminados, vea [Crear prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 Una vez empaquetadas, puede llamar a los métodos de las funciones del mismo modo que se llama a los métodos de cualquier otra función estática.  La invocación de plataforma controla la función exportada subyacente de forma automática.  
  
 A la hora de diseñar una clase administrada para la invocación de plataforma, hay que tener en cuenta las relaciones que existen entre las clases y las funciones de archivos DLL.  Por ejemplo, puede:  
  
-   Declarar funciones de archivos DLL dentro de una clase existente.  
  
-   Crear una clase individual para cada función de un archivo DLL, de este modo las funciones se mantienen aisladas y resultan fáciles de encontrar.  
  
-   Crear una clase para un conjunto de funciones relacionadas de un archivo DLL para formar grupos lógicos y reducir la sobrecarga.  
  
 Puede dar a la clase y a sus métodos los nombres que desee.  Para obtener ejemplos que muestren cómo construir declaraciones .NET que se utilizan con la invocación de plataforma, vea [Cálculo de referencias de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## Vea también  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Identifying Functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)