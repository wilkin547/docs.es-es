---
title: Valores numéricos en .NET
ms.date: 10/18/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
ms.openlocfilehash: 3b95a322377e82249a0375af589df74c658fcbf4
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507421"
---
# <a name="numerics-in-net"></a>Valores numéricos en .NET

.NET proporciona una serie de tipos primitivos de entero numérico y de punto flotante, así como <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, que es un tipo entero sin límite inferior ni superior teórico, <xref:System.Numerics.Complex?displayProperty=nameWithType>, que representa números complejos y un conjunto de tipos habilitados para SIMD en el espacio de nombres <xref:System.Numerics>.
  
## <a name="integer-types"></a>Tipos enteros

.NET admite tipos enteros de 8, 16, 32 y 64 bits con signo y sin signo, que se enumeran en la tabla siguiente:
  
|Tipo|Con signo/sin signo|Tamaño (en bytes)|Valor mínimo|Valor máximo|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|Sin signo|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|Firmado|2|-32.768|32.767|  
|<xref:System.Int32?displayProperty=nameWithType>|Firmado|4|-2.147.483.648|2\.147.483.647|  
|<xref:System.Int64?displayProperty=nameWithType>|Firmado|8|-9.223.372.036.854.775.808|9\.223.372.036.854.775.807|  
|<xref:System.SByte?displayProperty=nameWithType>|Firmado|1|-128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|Sin signo|2|0|65.535|  
|<xref:System.UInt32?displayProperty=nameWithType>|Sin signo|4|0|4\.294.967.295|  
|<xref:System.UInt64?displayProperty=nameWithType>|Sin signo|8|0|18.446.744.073.709.551.615|  
  
Cada tipo de entero admite un conjunto de operadores aritméticos estándar. La clase <xref:System.Math?displayProperty=nameWithType> proporciona métodos para un conjunto más amplio de funciones matemáticas.

También puede trabajar con los bits individuales de un valor entero usando la clase <xref:System.BitConverter?displayProperty=nameWithType>.  

> [!NOTE]  
> Los tipos enteros sin signo no son conformes a CLS. Para obtener más información, consulte [Independencia del lenguaje y componentes independientes del lenguaje](language-independence-and-language-independent-components.md).

## <a name="biginteger"></a>BigInteger

La estructura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> es un tipo inmutable que representa un entero arbitrariamente grande cuyo valor, en teoría, no tiene ningún límite superior o inferior. Los métodos del tipo <xref:System.Numerics.BigInteger> son análogos a los de otros tipos integrales.
  
## <a name="floating-point-types"></a>Tipos de punto flotante

.NET incluye tres tipos primitivos de punto flotante, que se enumeran en la tabla siguiente:
  
|Tipo|Tamaño (en bytes)|Intervalo aproximado|Precisión|  
|----------|--------|---------------------|--------------------|  
|<xref:System.Single?displayProperty=nameWithType>|4|De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup>|De 6 a 9 dígitos aproximadamente|  
|<xref:System.Double?displayProperty=nameWithType>|8|De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup>|De 15 a 17 dígitos aproximadamente|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup>|28-29 dígitos|  
  
Los tipos <xref:System.Single> y <xref:System.Double> admiten valores especiales que representan un valor no numérico e infinito. Por ejemplo, el tipo <xref:System.Double> proporciona los siguientes valores: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> y <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>. Los métodos <xref:System.Double.IsNaN%2A?displayProperty=nameWithType>, <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType>, <xref:System.Double.IsPositiveInfinity%2A?displayProperty=nameWithType> y <xref:System.Double.IsNegativeInfinity%2A?displayProperty=nameWithType> se usan para comprobar estos valores especiales.

Cada tipo de punto flotante admite un conjunto de operadores aritméticos estándar. La clase <xref:System.Math?displayProperty=nameWithType> proporciona métodos para un conjunto más amplio de funciones matemáticas. .NET Core 2.0 y versiones posteriores incluyen la clase <xref:System.MathF?displayProperty=nameWithType> que proporciona métodos que aceptan argumentos del tipo <xref:System.Single>.

También puede trabajar con bits individuales de valores <xref:System.Double> y <xref:System.Single> usando la clase <xref:System.BitConverter?displayProperty=nameWithType>. La estructura <xref:System.Decimal?displayProperty=nameWithType> tiene sus propios métodos, <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> y <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29>, para trabajar con los bits individuales de un valor decimal, así como su propio conjunto de métodos para realizar algunas operaciones matemáticas adicionales.
  
Los tipos <xref:System.Double> y <xref:System.Single> están diseñados para usarse con valores que, por su naturaleza, no son precisos (por ejemplo, la distancia entre dos estrellas) y para aplicaciones en las que no se necesita un alto grado de precisión ni un mínimo error de redondeo. Use el tipo <xref:System.Decimal?displayProperty=nameWithType> para los casos en los que se necesite una mayor precisión y se deban minimizar los errores de redondeo.

> [!NOTE]
> El tipo <xref:System.Decimal> no elimina la necesidad de redondeo. En su lugar, minimiza los errores debido al redondeo.
  
## <a name="complex"></a>Complex

La estructura <xref:System.Numerics.Complex?displayProperty=nameWithType> representa un número complejo, es decir, un número con una parte de número real y una parte de número imaginario. Admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita e implícita, así como métodos matemáticos, algebraicos y trigonométricos.  
  
## <a name="simd-enabled-types"></a>Tipos habilitados para SIMD

El espacio de nombres <xref:System.Numerics> incluye un conjunto de tipos habilitados para SIMD para .NET. Las operaciones SIMD (Single Instruction Multiple Data) se pueden paralelizar en el nivel de hardware. Eso aumenta el rendimiento de los cálculos vectorizados, que son comunes en aplicaciones matemáticas, científicas y gráficas.
  
Los tipos habilitados para SIMD para .NET incluyen los siguientes:

- Los tipos <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> y <xref:System.Numerics.Vector4>, que representan vectores con los valores <xref:System.Single> 2, 3 y 4.

- Dos tipos de matriz: <xref:System.Numerics.Matrix3x2>, que representa una matriz de 3x2, y <xref:System.Numerics.Matrix4x4>, que representa una matriz de 4x4.

- El tipo <xref:System.Numerics.Plane>, que representa un plano en un espacio tridimensional.

- El tipo <xref:System.Numerics.Quaternion>, que representa un vector que se usa para codificar rotaciones físicas tridimensionales.

- El tipo <xref:System.Numerics.Vector%601>, que representa un vector de un tipo numérico especificado y proporciona un amplio conjunto de operadores que aprovechan la compatibilidad con SIMD. El recuento de una instancia <xref:System.Numerics.Vector%601> es fijo, pero su valor <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> depende de la CPU de la máquina, en la que se ejecuta el código.
  > [!NOTE]
  > El <xref:System.Numerics.Vector%601> tipo no está incluido en .NET Framework. Debe instalar el paquete NuGet [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) para acceder a este tipo.
  
Los tipos habilitados para SIMD se implementan de tal forma que se pueden utilizar con hardware no habilitado para SIMD o compiladores JIT. Para aprovechar las instrucciones de SIMD, las aplicaciones de 64 bits las debe ejecutar el entorno en tiempo de ejecución que usa el compilador RyuJIT, que se incluye en .NET Core y en .NET Framework 4.6 y versiones posteriores. Agrega compatibilidad con SIMD cuando se usan procesadores de 64 bits como destino.

Para obtener más información, vea [Uso de tipos numéricos acelerados por SIMD](simd.md).

## <a name="see-also"></a>Vea también

- [Cadenas con formato numérico estándar](base-types/standard-numeric-format-strings.md)
