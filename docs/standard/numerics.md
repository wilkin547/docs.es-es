---
title: "Valores numéricos en .NET Core"
description: "Valores numéricos en .NET Core"
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6b8696be-55f5-4b66-98f3-69ff827c2c49
translationtype: Human Translation
ms.sourcegitcommit: d5c7a18af16b4f3416e84b6cf86f0f78f28948da
ms.openlocfilehash: 2930bf6879df3cd16cbd0221ae6dfcba9b41de2e

---

# <a name="numerics-in-net-core"></a>Valores numéricos en .NET Core

.NET Core admite los tipos primitivos estándar de entero numérico y de punto flotante, así como [System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger), un tipo entero sin límite inferior ni superior teórico, [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex), un tipo que representa números complejos y un conjunto de tipos de vector habilitados para Single Instruction Multiple Data ([SIMD](https://en.wikipedia.org/wiki/SIMD)) en el espacio de nombres [System.Numerics](https://docs.microsoft.com/dotnet/core/api/System.Numerics). 

## <a name="integral-types"></a>Tipos enteros

.NET Core admite enteros con signo y sin signo con una longitud de entre un byte y ocho bytes. En la tabla siguiente se enumeran los tipos enteros y su tamaño, se indica si tienen signo o no, y se documenta su intervalo. Todos los enteros son tipos de valor. 

Tipo | Con signo/sin signo | Tamaño (bytes) | Valor mínimo | Valor máximo
---- | --------------- | ------------ | ------------- | -------------
[System.Byte](https://docs.microsoft.com/dotnet/core/api/System.Byte) | Sin signo | 1 | 0 | 255
[System.Int16](https://docs.microsoft.com/dotnet/core/api/System.Int16) | Firmado | 2 | -32.768 | 32.767
[System.Int32](https://docs.microsoft.com/dotnet/core/api/System.Int32) | Firmado | 4 | -2.147.483.648 | 2.147.483.647
[System.Int64](https://docs.microsoft.com/dotnet/core/api/System.Int64) | Firmado | 8 | -9.223.372.036.854.775.808 | 9.223.372.036.854.775.807
[System.SByte](https://docs.microsoft.com/dotnet/core/api/System.SByte) | Firmado | 1 | -128 | 127
[System.UInt16](https://docs.microsoft.com/dotnet/core/api/System.UInt16) | Sin signo | 2 | 0 | 65.535
[System.UInt32](https://docs.microsoft.com/dotnet/core/api/System.UInt32) | Sin signo | 4 | 0 | 4.294.967.295
[System.UInt64](https://docs.microsoft.com/dotnet/core/api/System.UInt64) | Sin signo | 8 | 0 | 18.446.744.073.709.551.615

Cada tipo integral admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita. Cada entero también incluye métodos para realizar comparaciones de igualdad y comparaciones relativas, para convertir la representación de cadena de un número en ese entero y para convertir un entero en su representación de cadena. Algunas operaciones matemáticas adicionales más allá de las que controlan los operadores estándar, como el redondeo y la identificación del valor mayor o menor de dos números enteros, están disponibles con la clase [System.Math](https://docs.microsoft.com/dotnet/core/api/System.Math). También puede trabajar con los bits individuales de un valor entero mediante la clase [System.BitConverter](https://docs.microsoft.com/dotnet/core/api/System.BitConverter). 
     
Tenga en cuenta que los tipos enteros sin signo no son conformes a CLS. Para obtener más información, consulte [.NET Common Type System & Common Language Specification](common-type-system.md) (Common Type System y Common Language Specification de .NET).

## <a name="floating-point-types"></a>Tipos de punto flotante

.NET Core incluye tres tipos primitivos de punto flotante, que se enumeran en la tabla siguiente. 

Tipo | Tamaño (bytes) | Valor mínimo | Valor máximo
---- | ------------ | ------------- | -------------
[System.Double](https://docs.microsoft.com/dotnet/core/api/System.Double) | 8 | -1,79769313486232e308 | -1,79769313486232e308
[System.Single](https://docs.microsoft.com/dotnet/core/api/System.Single) | 4 | -3,402823e38 | -3,402823e38
[System.Decimal](https://docs.microsoft.com/dotnet/core/api/System.Decimal) | 16 | -79.228.162.514.264.337.593.543.950.335 | 79.228.162.514.264.337.593.543.950.335
   
Cada tipo de punto flotante admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita. Cada uno incluye también métodos para realizar comparaciones de igualdad y comparaciones relativas, para convertir la representación de cadena de un número de punto flotante y para convertir un número de punto flotante en su representación de cadena. Algunas operaciones matemáticas, algebraicas y trigonométricas adicionales están disponibles con la clase `Math`. También puede trabajar con bits individuales de valores `Double` y `Single` usando la clase `BitConverter`. La estructura `Decimal` tiene sus propios métodos, `Decimal.GetBits` y `Decimal.Decimal(Int32())`, para trabajar con los bits individuales de un valor decimal, así como su propio conjunto de métodos para realizar algunas operaciones matemáticas adicionales. 

Los tipos `Double` y `Single` están diseñados para usarse con valores que, por su naturaleza, no son precisos (como la distancia entre dos estrellas del sistema solar) y para aplicaciones en las que no se necesita un alto grado de precisión y pequeño error de redondeo. Debe usar el tipo `Decimal` para los casos en los que se necesite una mayor precisión y cuando no se quieran errores de redondeo.

## <a name="biginteger"></a>BigInteger

[System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger) es un tipo inmutable que representa un entero arbitrariamente grande cuyo valor en teoría no tiene ningún límite superior o inferior. Los métodos del tipo `BigInteger` son análogos a los de otros tipos integrales.  

## <a name="complex"></a>Complex

El tipo [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex) representa un número complejo, es decir, un número con una parte de número real y una parte de número imaginario. Admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita, así como métodos matemáticos, algebraicos y trigonométricos. 

## <a name="simd-enabled-vector-types"></a>Tipos de vector habilitados para SIMD

El espacio de nombres `System.Numerics` incluye un conjunto de tipos de vector habilitados para SIMD para .NET Core. SIMD permite que algunas operaciones se ejecuten en paralelo en el nivel de hardware, con lo que se obtienen grandes mejoras de rendimiento en aplicaciones matemáticas, científicas y de gráficos que realizan cálculos con vectores. 

Los tipos de vector habilitados para SIMD en .NET Core incluyen los siguientes: 

* Los tipos [System.Numerics.Vector2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector2), [System.Numerics.Vector3](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector3) y [System.Numerics.Vector4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector4), que son vectores de 2, 3 y 4 dimensiones del tipo `Single`.

* La estructura [Vector&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector-1), que permite crear un vector de cualquier tipo numérico primitivo. Los tipos numéricos primitivos incluyen todos los tipos numéricos en el espacio de nombres System, salvo para Decimal.

* Dos tipos de matriz: [System.Numerics.Matrix3x2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix3x2), que representa una matriz de 3x2, y [System.Numerics.Matrix4x4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix4x4), que representa una matriz de 4x4. 

* El tipo [System.Numerics.Plane](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Plane), que representa un plano tridimensional, y el tipo [System.Numerics.Quaternion](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Quaternion), que representa un vector que se usa para codificar rotaciones físicas tridimensionales.



<!--HONumber=Nov16_HO3-->


