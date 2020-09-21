---
title: 'Información general sobre interoperabilidad: Guía de programación de C#'
description: Aprenda sobre la interoperabilidad entre C# y el código no administrado, como la invocación de plataforma, la interoperabilidad de C++, la exposición de componentes COM a C# y la exposición de C# a COM.
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
ms.openlocfilehash: 41ee25397d519f189b462291d823586113c78b67
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541544"
---
# <a name="interoperability-overview-c-programming-guide"></a>Información general sobre interoperabilidad (Guía de programación de C#)
En el tema se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.  
  
## <a name="platform-invoke"></a>Invocación de plataforma  
 La *invocación de plataforma* es un servicio que permite al código administrado llamar a funciones no administradas que se implementan en bibliotecas de vínculos dinámicos (DLL), como las de la API de Microsoft Windows. Busca y llama a una función exportada y calcula las referencias de sus argumentos (enteros, cadenas, matrices, estructuras etc.) a través de los límites de interoperación según sea necesario.  
  
Para más información, consulte [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md) y [Procedimiento Utilizar la invocación de plataforma para reproducir un archivo de sonido](./how-to-use-platform-invoke-to-play-a-wave-file.md).
  
> [!NOTE]
> [Common Language Runtime](../../../standard/clr.md) (CLR) administra el acceso a los recursos del sistema. Si se llama al código no administrado que está fuera de CLR, se omite este mecanismo de seguridad y, por lo tanto, existe un riesgo de seguridad. Por ejemplo, el código no administrado podría llamar directamente a recursos en código no administrado, omitiendo los mecanismos de seguridad de CLR. Para obtener más información, vea [Seguridad en .NET](../../../standard/security/index.md).  
  
## <a name="c-interop"></a>Interoperabilidad de C++  
 Puede usar la interoperabilidad de C++, también conocida como It Just Works (IJW), para encapsular una clase de C++ nativa de modo que el código creado en C# o en otro lenguaje de .NET pueda consumirla. Para ello, escriba código de C++ para encapsular un componente DLL o COM nativo. A diferencia de otros lenguajes de .NET, Visual C++ cuenta con compatibilidad de interoperabilidad que permite que haya código administrado y no administrado en la misma aplicación, e incluso en el mismo archivo. Después, compile el código de C++ mediante el modificador del compilador **/clr** para generar un ensamblado administrado. Finalmente, agregue una referencia al ensamblado en el proyecto de C# y use los objetos encapsulados igual que usaría otras clases administradas.  
  
## <a name="exposing-com-components-to-c"></a>Exponer componentes COM en C\#
 Puede usar un componente COM de un proyecto de C#. Los pasos generales son los siguientes:  
  
1. Busque un componente COM para usarlo y registrarlo. Use regsvr32.exe para registrar un componente DLL COM o para anular su registro.  
  
2. Agregue al proyecto una referencia a la biblioteca de tipos o al componente COM.  
  
     Al agregar la referencia, Visual Studio usa [Tlbimp.exe (importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md), que toma una biblioteca de tipos como entrada para generar un ensamblado de interoperabilidad de .NET. El ensamblado, también denominado "contenedor RCW", contiene las clases e interfaces administradas que encapsulan las interfaces y clases COM que se encuentran en la biblioteca de tipos. Visual Studio agrega al proyecto una referencia al ensamblado generado.  
  
3. Cree una instancia de una clase definida en el RCW. Este, a su vez, crea una instancia del objeto COM.  
  
4. Use el objeto igual que usa otros objetos administrados. Cuando el objeto sea reclamado por la recolección de elementos no utilizados, la instancia del objeto COM también se liberará de la memoria.  
  
 Para obtener más información, vea [Exponer componentes COM en .NET Framework](../../../framework/interop/exposing-com-components.md).  
  
## <a name="exposing-c-to-com"></a>Exponer C# en COM  
 Los clientes COM pueden consumir tipos de C# que se han expuesto correctamente. Los pasos básicos para exponer tipos de C# son los siguientes:  
  
1. Agregue atributos de interoperabilidad al proyecto de C#.  
  
     Puede hacer que un ensamblado COM sea visible al modificar las propiedades del proyecto de Visual C#. Para obtener más información, vea [Información de ensamblado (Cuadro de diálogo)](/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2. Genere una biblioteca de tipos COM y regístrela para el uso de COM.  
  
     Puede modificar las propiedades del proyecto de Visual C# para registrar automáticamente el ensamblado de C# para la interoperabilidad COM. Visual Studio usa [Regasm.exe (herramienta de registro de ensamblados)](../../../framework/tools/regasm-exe-assembly-registration-tool.md), con el modificador de la línea de comandos `/tlb`, que toma un ensamblado administrado como entrada, para generar una biblioteca de tipos. Esta biblioteca de tipos describe los tipos `public` del ensamblado y agrega entradas del registro para que los clientes COM puedan crear clases administradas.  
  
 Para obtener más información, vea [Exponer componentes de .NET Framework en COM](../../../framework/interop/exposing-dotnet-components-to-com.md) y [Clase COM de ejemplo](./example-com-class.md).  
  
## <a name="see-also"></a>Vea también

- [Improving Interop Performance](/previous-versions/msp-n-p/ff647812(v=pandp.10)) (Mejorar el rendimiento interoperativo)
- [Introducción a la interoperabilidad entre COM y .NET](/office/client-developer/outlook/pia/introduction-to-interoperability-between-com-and-net)
- [Información general sobre la interoperabilidad COM (Visual Basic)](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
- [Serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md)
- [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)
- [Guía de programación de C#](../index.md)
