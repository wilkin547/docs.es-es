---
title: "Informaci&#243;n general sobre interoperabilidad (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, interoperabilidad"
  - "interoperabilidad de C++"
  - "interoperabilidad COM"
  - "interoperabilidad, acerca de la interoperabilidad"
  - "invocación de plataforma"
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# Informaci&#243;n general sobre interoperabilidad (Gu&#237;a de programaci&#243;n de C#)
En este tema se describen métodos para habilitar la interoperabilidad entre el código administrado y no administrado de C\#.  
  
## Invocación de plataforma  
 La *invocación de plataforma* es un servicio que habilita el código administrado para llamar a funciones no administradas implementadas en bibliotecas de vínculos dinámicos \(DLL\), como las que se encuentran en la API de Microsoft Win32.  Localiza e invoca una función exportada y calcula las referencias a sus argumentos \(enteros, cadenas, matrices, estructuras, etc.\) dentro de los límites de la interoperabilidad, según sea necesario.  
  
 Para obtener más información, vea [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md) y [Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md) \(CLR\) administra el acceso a los recursos del sistema.  Llamar a código no administrado que se encuentra fuera de CLR omite este mecanismo de seguridad y, por consiguiente, presenta un riesgo de seguridad.  Por ejemplo, un código no administrado podría llamar directamente a recursos en código no administrado, lo que omitiría los mecanismos de seguridad de CLR.  Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## Interoperabilidad de C\+\+  
 Puede utilizar la interoperabilidad de C\+\+, también conocida como IJW \(It Just Works\), para encapsular una clase de C\+\+ nativa de forma que la pueda utilizar el código creado en C\# u otro lenguaje de .NET Framework.  Para ello, escriba código de C\+\+ que encapsule un componente DLL o COM nativo.  A diferencia de otros lenguajes de .NET Framework, [!INCLUDE[vcprvc](../../../csharp/programming-guide/interop/includes/vcprvc-md.md)] cuenta con compatibilidad de interoperabilidad, que permite que haya código administrado y no administrado en la misma aplicación, e incluso en el mismo archivo.  A continuación, se genera el código de C\+\+ utilizando el modificador del compilador **\/clr** para generar un ensamblado administrado.  Por último, se agrega una referencia al ensamblado en el proyecto de C\# y se usan los objetos encapsulados de la misma forma que se utilizan otras clases administradas.  
  
## Exponer componentes COM a C\#  
 Puede usar un componente COM de un proyecto de C\#.  A continuación se enumeran los pasos generales:  
  
1.  Busque un componente COM que desee usar y regístrelo.  Use regsvr32.exe para registrar o anular el registro de un archivo DLL COM.  
  
2.  Agregue al proyecto una referencia a la biblioteca de tipos o el componente COM.  
  
     Al agregar la referencia, [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] usa el [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md), que acepta una biblioteca de tipos como entrada, para generar un ensamblado de interoperabilidad de .NET Framework.  El ensamblado, también denominado contenedor RCW \(Runtime Callable Wrapper\), contiene clases e interfaces administradas que encapsulan las clases e interfaces COM que se encuentran en la biblioteca de tipos.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] agrega al proyecto una referencia para el ensamblado generado.  
  
3.  Cree una instancia de una clase definida en RCW.  Esto, a su vez, crea una instancia del objeto COM.  
  
4.  Use el objeto de la misma forma que utiliza otros objetos administrados.  Cuando la recolección de elementos no utilizados reclama el objeto, la instancia del objeto COM también se libera de la memoria.  
  
 Para obtener más información, vea [Exposing COM Components to the .NET Framework](../Topic/Exposing%20COM%20Components%20to%20the%20.NET%20Framework.md).  
  
## Exponer C\# a COM  
 Los clientes COM pueden usar tipos C\# que se hayan expuesto correctamente.  A continuación se muestran los pasos básicos para exponer tipos C\#:  
  
1.  Agregar atributos de interoperabilidad al proyecto de C\#.  
  
     Puede hacer que un ensamblado sea visible a través de COM; para ello, modifique las propiedades del proyecto de [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)].  Para obtener más información, vea [Información de ensamblado \(Cuadro de diálogo\)](/visual-studio/ide/reference/assembly-information-dialog-box).  
  
2.  Generar una biblioteca de tipos COM y registrarla para el uso de COM.  
  
     Puede modificar las propiedades del proyecto [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] para registrar automáticamente el ensamblado de C\# para interoperabilidad COM.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] usa [Regasm.exe \(Assembly Registration Tool\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md), mediante el modificador de la línea de comandos `/tlb`, que toma un ensamblado administrado como entrada, para generar una biblioteca de tipos.  Esta biblioteca de tipos describe los tipos `public` del ensamblado y agrega entradas del Registro para que los clientes COM puedan crear clases administradas.  
  
 Para obtener más información, vea [Exposing .NET Framework Components to COM](../Topic/Exposing%20.NET%20Framework%20Components%20to%20COM.md) y [Clase COM de ejemplo](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## Vea también  
 [Mejora de rendimiento de Interoperabilidad](http://go.microsoft.com/fwlink/?LinkId=99564)   
 [introducción a la interoperabilidad COM](http://go.microsoft.com/fwlink/?LinkId=112406)   
 [Cálculo de referencias entre código administrado y no administrado](http://go.microsoft.com/fwlink/?LinkId=112398)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)