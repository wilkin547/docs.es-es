---
title: Interoperar con código no administrado
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 12183f390a5178f038c6dd2122a72a33e31ae0ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457969"
---
# <a name="interoperating-with-unmanaged-code"></a>Interoperar con código no administrado

.NET Framework promueve la interacción con componentes COM, servicios COM+, bibliotecas de tipos externas y muchos servicios del sistema operativo. Los tipos de datos, las firmas de método y los mecanismos de control de errores varían entre los modelos de objetos administrados y no administrados. Para simplificar la interoperación entre los componentes de .NET Framework y el código no administrado, así como para facilitar la ruta de migración, Common Language Runtime oculta a los clientes y servidores las diferencias en estos modelos de objetos.

El código que se ejecuta bajo el control del tiempo de ejecución se denomina código administrado. Por el contrario, el código que se ejecuta fuera del tiempo de ejecución se denomina código no administrado. Los componentes COM, las interfaces ActiveX y las funciones de la API de Windows son ejemplos de código no administrado.

## <a name="in-this-section"></a>En esta sección

[Exponer componentes COM en .NET Framework](exposing-com-components.md)  
Se describe cómo usar los componentes COM desde las aplicaciones de .NET Framework.

[Exponer componentes de .NET Framework en COM](exposing-dotnet-components-to-com.md)  
Se describe cómo usar los componentes de .NET Framework desde las aplicaciones COM.

[Consumir funciones DLL no administradas](consuming-unmanaged-dll-functions.md)  
Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.

[Serialización de interoperabilidad](interop-marshaling.md)  
Se describe la serialización de la interoperabilidad COM y la invocación de plataforma.

[Cómo: Asignar resultados HRESULT y excepciones](how-to-map-hresults-and-exceptions.md)  
Se describe la asignación entre las excepciones y los valores HRESULT.

[Equivalencia de tipos y tipos de interoperabilidad incrustados](type-equivalence-and-embedded-interop-types.md)  
Describe cómo la información de tipo para tipos COM está insertada en los ensamblados y cómo Common Language Runtime determina la equivalencia de los tipos COM insertados.

[Cómo: para generar ensamblados de interoperabilidad primarios mediante Tlbimp.exe](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Describe cómo producir ensamblados de interoperabilidad primarios con *Tlbimp.exe*  (importador de bibliotecas de tipos).

[Cómo: Registrar ensamblados de interoperabilidad primarios](how-to-register-primary-interop-assemblies.md)  
Describe cómo registrar los ensamblados de interoperabilidad primarios antes de hacer referencia a ellos en los proyectos.

[Interoperabilidad COM sin registro](registration-free-com-interop.md)  
Describe cómo la interoperabilidad COM puede activar componentes sin usar el Registro de Windows.

[Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro](configure-net-framework-based-com-components-for-reg.md)  
Describe cómo crear un manifiesto de aplicación y cómo crear e insertar un manifiesto de componente.

## <a name="related-sections"></a>Secciones relacionadas

[Contenedores COM](../../standard/native-interop/com-wrappers.md)  
Describe los contenedores proporcionados por la interoperabilidad COM.
