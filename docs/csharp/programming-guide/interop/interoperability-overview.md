---
title: "Información general sobre interoperabilidad (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 5084c4af3334c39f844fec67a1ab05dd9443bf27
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="interoperability-overview-c-programming-guide"></a>Información general sobre interoperabilidad (Guía de programación de C#)
En el tema se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.  
  
## <a name="platform-invoke"></a>Invocación de plataforma  
 La *invocación de plataforma* es un servicio que permite al código administrado llamar a funciones no administradas que se implementan en bibliotecas de vínculos dinámicos (DLL), como las de la API de Microsoft Win32. Busca y llama a una función exportada y calcula las referencias de sus argumentos (enteros, cadenas, matrices, estructuras etc.) a través de los límites de interoperación según sea necesario.  
  
 Para obtener más información, vea [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md) y [Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  [Common Language Runtime](../../../standard/clr.md) (CLR) administra el acceso a los recursos del sistema. Si se llama al código no administrado que está fuera de CLR, se omite este mecanismo de seguridad y, por lo tanto, existe un riesgo de seguridad. Por ejemplo, el código no administrado podría llamar directamente a recursos en código no administrado, omitiendo los mecanismos de seguridad de CLR. Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## <a name="c-interop"></a>Interoperabilidad de C++  
 Puede usar la interoperabilidad de C++, también conocida como It Just Works (IJW), para encapsular una clase de C++ nativa de modo que el código creado en C# o en otro lenguaje de .NET Framework pueda consumirla. Para ello, escriba código de C++ para encapsular un componente DLL o COM nativo. A diferencia de otros lenguajes de .NET Framework, [!INCLUDE[vcprvc](../../../csharp/programming-guide/interop/includes/vcprvc_md.md)] cuenta con compatibilidad de interoperabilidad que permite que haya código administrado y no administrado en la misma aplicación, e incluso en el mismo archivo. Después, compile el código de C++ mediante el modificador del compilador **/clr** para generar un ensamblado administrado. Finalmente, agregue una referencia al ensamblado en el proyecto de C# y use los objetos encapsulados igual que usaría otras clases administradas.  
  
## <a name="exposing-com-components-to-c"></a>Exponer componentes COM en C#  
 Puede usar un componente COM de un proyecto de C#. Los pasos generales son los siguientes:  
  
1.  Busque un componente COM para usarlo y registrarlo. Use regsvr32.exe para registrar un componente DLL COM o para anular su registro.  
  
2.  Agregue al proyecto una referencia a la biblioteca de tipos o al componente COM.  
  
     Al agregar la referencia, [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] usa [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), que toma una biblioteca de tipos como entrada para generar un ensamblado de interoperabilidad de .NET Framework. El ensamblado, también denominado "contenedor RCW", contiene las clases e interfaces administradas que encapsulan las interfaces y clases COM que se encuentran en la biblioteca de tipos. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] agrega al proyecto una referencia al ensamblado generado.  
  
3.  Cree una instancia de una clase definida en el RCW. Este, a su vez, crea una instancia del objeto COM.  
  
4.  Use el objeto igual que usa otros objetos administrados. Cuando el objeto sea reclamado por la recolección de elementos no utilizados, la instancia del objeto COM también se liberará de la memoria.  
  
 Para obtener más información, vea [Exponer componentes COM en .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).  
  
## <a name="exposing-c-to-com"></a>Exponer C# en COM  
 Los clientes COM pueden consumir tipos de C# que se han expuesto correctamente. Los pasos básicos para exponer tipos de C# son los siguientes:  
  
1.  Agregue atributos de interoperabilidad al proyecto de C#.  
  
     Puede hacer que un ensamblado COM sea visible modificando las propiedades del proyecto de [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)]. Para obtener más información, vea [Información de ensamblado (Cuadro de diálogo)](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2.  Genere una biblioteca de tipos COM y regístrela para el uso de COM.  
  
     Puede modificar las propiedades del proyecto de [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] para registrar automáticamente el ensamblado de C# para la interoperabilidad COM. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] usa [Regasm.exe (herramienta de registro de ensamblados)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb) con el modificador de la línea de comandos `/tlb`, que toma un ensamblado administrado como entrada, para generar una biblioteca de tipos. Esta biblioteca de tipos describe los tipos `public` del ensamblado y agrega entradas del registro para que los clientes COM puedan crear clases administradas.  
  
 Para obtener más información, vea [Exponer componentes de .NET Framework en COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) y [Clase COM de ejemplo](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## <a name="see-also"></a>Vea también  
 [Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564)  (Mejorar el rendimiento interoperativo)  
 [Introducción a la interoperabilidad COM](http://go.microsoft.com/fwlink/?LinkId=112406)   
 [Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398)  (Calcular las referencias entre el código administrado y el código no administrado)  
 [Interoperar con código no administrado](https://msdn.microsoft.com/library/sd10k43k)   
 [Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)
