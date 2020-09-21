---
title: Empaquetar un ensamblado de .NET Framework para COM
description: Empaquete un ensamblado .NET para COM. Recopile la lista de tipos que las aplicaciones COM pueden consumir, las instrucciones de control de versiones e implementación y la biblioteca de tipos.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
ms.openlocfilehash: 5fde7f7f00aadf4d941d4ffe522453970b67e9e2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554135"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a>Empaquetar un ensamblado de .NET Framework para COM

Los programadores de COM pueden beneficiarse de la siguiente información sobre los tipos administrados que piensan incluir en su aplicación:

- Una lista de tipos que las aplicaciones COM pueden consumir

  Algunos tipos administrados son invisibles para COM; algunos son visibles, pero no pueden crearse y otros son visibles y se pueden crear. Un ensamblado puede contener cualquier combinación de tipos invisibles, visibles, que no se pueden crear y que se pueden crear. Para completar, identifique los tipos de un ensamblado que se van a exponer a COM, especialmente cuando esos tipos son un subconjunto de los tipos expuestos a .NET Framework.

  Para obtener información adicional, vea [Habilitar tipos de .NET para la interoperación](../../standard/native-interop/qualify-net-types-for-interoperation.md).

- Instrucciones de control de versiones

  Las clases administradas que implementan la interfaz de clase (una interfaz de COM generada por la interoperabilidad) están sujetas a restricciones de control de versiones.

  Para obtener instrucciones sobre el uso de la interfaz de clase, consulte [Presentar la interfaz de clase](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).

- Instrucciones de implementación

  Los ensamblados con nombre seguro que están firmados por un editor se pueden instalar en la caché global de ensamblados. Los ensamblados no firmados deben instalarse en el equipo del usuario como ensamblados privados.

  Para más información, vea [Consideraciones de seguridad sobre ensamblados](../../standard/assembly/security-considerations.md).

- Inclusión de la biblioteca de tipos

  La mayoría de los tipos requiere una biblioteca de tipos cuando una aplicación COM los consume. Puede generar una biblioteca de tipos o hacer que los desarrolladores de COM realicen esta tarea. Windows SDK proporciona las opciones siguientes para generar una biblioteca de tipos:

  - [Exportador de la biblioteca de tipos](#cpconpackagingassemblyforcomanchor1)

  - [TypeLibConverter (clase)](#cpconpackagingassemblyforcomanchor2)

  - [Herramienta de registro de ensamblados](#cpconpackagingassemblyforcomanchor3)

  - [Herramienta de instalación de servicios de .NET](#cpconpackagingassemblyforcomanchor4)

  Independientemente del mecanismo que elija, en la biblioteca de tipos generada solo se incluyen los tipos públicos definidos en el ensamblado que se proporciona.

Para obtener instrucciones, vea [Cómo: Insertar bibliotecas de tipos como recursos de Win32 en aplicaciones basadas en .NET](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a>Exportador de la biblioteca de tipos

El [exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) es una herramienta de línea de comandos que convierte las clases e interfaces contenidas en un ensamblado en una biblioteca de tipos COM. Una vez que la información de tipos de la clase está disponible, los clientes COM pueden crear una instancia de la clase de .NET y llamar a los métodos de la instancia, como si se tratase de un objeto COM. Tlbexp.exe convierte todo el ensamblado al mismo tiempo. No se puede utilizar Tlbexp.exe para generar información de tipos correspondiente a un subconjunto de los tipos definidos en un ensamblado.

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a>TypeLibConverter (clase)

La clase <xref:System.Runtime.InteropServices.TypeLibConverter>, que se encuentra en el espacio de nombres **System.Runtime.Interop**, convierte las clases e interfaces de un ensamblado en una biblioteca de tipos COM. Esta API genera la misma información de tipos que el Exportador de la biblioteca de tipos, descrito en la sección anterior.

La **clase TypeLibConverter** implementa el <xref:System.Runtime.InteropServices.ITypeLibConverter>.

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a>Herramienta de registro de ensamblados

La [Herramienta de registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) puede generar y registrar una biblioteca de tipos cuando se aplica la opción **/tlb:** . Los clientes COM requieren que las bibliotecas de tipos se instalen en el Registro de Windows. Sin esta opción, Regasm.exe solo registra los tipos en un ensamblado, no la biblioteca de tipos. Registrar los tipos en un ensamblado y registrar la biblioteca de tipos son actividades distintas.

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a>Herramienta de instalación de servicios de .NET

La [Herramienta de instalación de servicios de .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) agrega clases administradas a servicios de componentes de Windows 2000 y combina varias tareas en una única herramienta. Además de cargar y registrar un ensamblado, Regsvcs.exe puede generar, registrar e instalar la biblioteca de tipos en una aplicación COM+ 1.0 existente.

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [Exponer componentes de .NET Framework en COM](exposing-dotnet-components-to-com.md)
- [Habilitar tipos de .NET para la interoperación](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [Presentar la interfaz de clase](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [Consideraciones de seguridad sobre ensamblados](../../standard/assembly/security-considerations.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../tools/tlbexp-exe-type-library-exporter.md)
- [Registrar ensamblados con COM](registering-assemblies-with-com.md)
- [Cómo: Insertar bibliotecas de tipos como recursos de Win32 en aplicaciones](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))
