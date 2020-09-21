---
title: Procedimiento para registrar ensamblados de interoperabilidad primarios
description: Registre ensamblados de interoperabilidad primarios mediante la herramienta de registro de ensamblados (Regasm.exe) y lea sobre otros problemas relacionados con ensamblados de interoperabilidad.
ms.date: 03/30/2017
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
ms.openlocfilehash: 09b283712a66805669154c720dff5c2c5f910bf4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547185"
---
# <a name="how-to-register-primary-interop-assemblies"></a>Procedimiento para registrar ensamblados de interoperabilidad primarios

Las clases solo se pueden serializar con la interoperabilidad COM y siempre se serializan como interfaces. En algunos casos, la interfaz usada para calcular las referencias de la clase se conoce como interfaz de clase. Para obtener información sobre cómo invalidar la interfaz de clase con una interfaz de su elección, vea [Contenedor CCW](../../standard/native-interop/com-callable-wrapper.md).

 Aunque cualquier desarrollador que quiera usar tipos COM en una aplicación .NET Framework puede generar un ensamblado de interoperabilidad, hacerlo supone un problema. Cada vez que un desarrollador importa y firma una biblioteca de tipos COM, crea un conjunto de tipos únicos que son incompatibles con los que importe y firme otro programador. La solución a este problema de incompatibilidad de tipos es que cada desarrollador obtenga el ensamblado de interoperabilidad principal firmado y suministrado por el proveedor.

 Si tiene previsto exponer tipos COM de terceros en otras aplicaciones, use siempre el ensamblado de interoperabilidad primario proporcionado por el mismo editor que la biblioteca de tipos que define. Además de garantizar la compatibilidad de tipos, los ensamblados de interoperabilidad primarios suelen estar personalizados por el proveedor para mejorar la interoperabilidad.

 Aunque no tenga pensado exponer tipos COM de terceros, el uso de ensamblados de interoperabilidad primarios puede facilitar la tarea de interoperar con componentes COM. Sin embargo, esta estrategia no ofrece aislamiento de los cambios que un proveedor pudiera hacer a los tipos definidos en un ensamblado de interoperabilidad primario. Cuando la aplicación requiera dicho aislamiento, genere su propio ensamblado de interoperabilidad en lugar de usar el ensamblado de interoperabilidad primario.

 Debe registrar todos los ensamblados de interoperabilidad primarios adquiridos en el equipo de desarrollo antes de hacer referencia a ellos con Visual Studio. Visual Studio busca y usa un ensamblado de interoperabilidad primario la primera vez que haga referencia a un tipo de una biblioteca de tipos COM. Si Visual Studio no encuentra el ensamblado de interoperabilidad primario asociado a la biblioteca de tipos, le pide que lo adquiera o le ofrece la posibilidad de crear un ensamblado de interoperabilidad en su lugar. Del mismo modo, el [Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) usa también el registro para buscar ensamblados de interoperabilidad primarios.

 Aunque no es necesario registrar los ensamblados de interoperabilidad primarios a menos que tenga pensado usar Visual Studio, registrarlos ofrece dos ventajas:

- Un ensamblado de interoperabilidad primario registrado está marcado claramente bajo la clave del Registro de la biblioteca de tipos original. Registrarlo es la mejor manera de encontrar un ensamblado de interoperabilidad primario en el equipo.

- Puede evitar generar y usar un nuevo ensamblado de interoperabilidad accidentalmente si, en algún momento en el futuro, usa Visual Studio para hacer referencia a un tipo para el que tiene un ensamblado de interoperabilidad primario sin registrar.

Use la [herramienta Registro de ensamblados (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) para registrar un ensamblado de interoperabilidad primario.

## <a name="to-register-a-primary-interop-assembly"></a>Para registrar un ensamblado de interoperabilidad primario

1. En el símbolo del sistema, escriba:

     **regasm** *assemblyname*

     En este comando, *nombre_de_ensamblado* es el nombre de archivo del ensamblado que se va a registrar. Regasm.exe agrega una entrada para el ensamblado de interoperabilidad primario bajo la misma clave del Registro que la biblioteca de tipos original.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se registra el ensamblado de interoperabilidad primario `CompanyA.UtilLib.dll`.

```console
regasm CompanyA.UtilLib.dll
```

## <a name="see-also"></a>Vea también

- [Programar con ensamblados de interoperabilidad primarios](/previous-versions/dotnet/netframework-4.0/baxfadst(v=vs.100))
- [Búsqueda de ensamblados de interoperabilidad primarios](/previous-versions/dotnet/netframework-4.0/y06sxw56(v=vs.100))
- [Redistribuir ensamblados de interoperabilidad primarios](/previous-versions/dotnet/netframework-4.0/w0dt2w20(v=vs.100))
