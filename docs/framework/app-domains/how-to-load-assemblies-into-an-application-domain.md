---
title: "C&#243;mo: Cargar ensamblados en un dominio de aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dominios de la aplicación, cargar ensamblados"
  - "cargar ensamblados"
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Cargar ensamblados en un dominio de aplicaci&#243;n
Existen varias formas de cargar un ensamblado en un dominio de aplicación.  La forma recomendada es utilizar el método `static` \(`Shared` en Visual Basic\) <xref:System.Reflection.Assembly.Load%2A> de la clase [System.Reflection.Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx).  Otras formas de cargar ensamblados son las que se indican a continuación:  
  
-   El método <xref:System.Reflection.Assembly.LoadFrom%2A> de la clase [Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) carga un ensamblado a partir de su ubicación de archivo.  Este método de carga de ensamblados utiliza un contexto de carga distinto.  
  
-   Los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> cargan un ensamblado en el contexto de sólo reflexión.  Los ensamblados cargados en este contexto pueden examinarse pero no pueden ejecutarse, lo que permite examinar los ensamblados destinados a otras plataformas.  Vea [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  El contexto de sólo reflexión es nuevo en la versión 2.0 de .NET Framework.  
  
-   Los métodos como <xref:System.AppDomain.CreateInstance%2A> y <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> de la clase <xref:System.AppDomain> permiten cargar ensamblados en un dominio de aplicación.  
  
-   El método <xref:System.Type.GetType%2A> de la clase <xref:System.Type> puede cargar ensamblados.  
  
-   El método <xref:System.AppDomain.Load%2A> de la clase <xref:System.AppDomain?displayProperty=fullName> permite cargar ensamblados, pero se utiliza principalmente para la interoperabilidad COM.  No debe utilizarse para cargar ensamblados en un dominio de aplicación distinto del dominio de aplicación desde el que se llama al método.  
  
> [!NOTE]
>  Si se inicia con la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará un ensamblado compilado con una versión de .NET Framework posterior a la actualmente cargada en el tiempo de ejecución.  Esto se aplica a la combinación de componentes principales y secundarios del número de versión.  
  
 Puede especificar la forma en que el código compilado Just\-In\-Time \(JIT\) de los ensamblados cargados se comparte entre los dominios de aplicación.  Para obtener más información, vea [Application Domains and Assemblies](http://msdn.microsoft.com/es-es/433b04ae-4ba8-4849-9dbd-79194f240346).  
  
## Ejemplo  
 En el siguiente código, se carga un ensamblado denominado "example.exe" o "example.dll" en el dominio de aplicación actual, se obtiene un tipo denominado `Example` del ensamblado, se obtiene un método sin parámetros denominado `MethodA` para ese tipo y se ejecuta el método.  Si desea una descripción completa de cómo obtener información de un ensamblado cargado, vea [Cargar y utilizar tipos dinámicamente](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Hosting Overview](http://msdn.microsoft.com/es-es/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)   
 [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Application Domains and Assemblies](http://msdn.microsoft.com/es-es/433b04ae-4ba8-4849-9dbd-79194f240346)