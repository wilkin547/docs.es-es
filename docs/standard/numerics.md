---
title: "Valores num&#233;ricos en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SIMD"
  - "System.Numerics.Vectors"
  - "vectores"
  - "ciencia computacional"
  - "Complex"
  - "valores numéricos"
  - "BigInteger"
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Valores num&#233;ricos en .NET Framework
.NET Framework admite los estándares primitivos de punto flotante y enteros numéricos, así como <xref:System.Numerics.BigInteger>, un tipo integral sin límite inferior ni superior teórico <xref:System.Numerics.Complex>, un tipo que representa números complejos y un conjunto de tipos de vector habilitados para SIMD en el <xref:System.Numerics> espacio de nombres.  
  
 Además, System.Numerics.Vectors, la biblioteca habilitados para SIMD de tipos vectory, se lanzó como un paquete de NuGet.  
  
## <a name="integral-types"></a>Tipos enteros  
 .NET Framework admite enteros con signo y sin signo con una longitud de entre un byte y ocho bytes. En la tabla siguiente se enumeran los tipos enteros y su tamaño, se indica si tienen signo o no, y se documenta su intervalo. Todos los enteros son tipos de valor.  
  
|Tipo|Con signo/sin signo|Tamaño (bytes)|Valor mínimo|Valor máximo|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=fullName>|Sin signo|1|0|255|  
|<xref:System.Int16?displayProperty=fullName>|Firmado|2|-32.768|32.767|  
|<xref:System.Int32?displayProperty=fullName>|Firmado|4|-2.147.483.648|2.147.483.647|  
|<xref:System.Int64?displayProperty=fullName>|Firmado|8|-9.223.372.036.854.775.808|9.223.372.036.854.775.807|  
|<xref:System.SByte?displayProperty=fullName>|Firmado|1|-128|127|  
|<xref:System.UInt16?displayProperty=fullName>|Sin signo|2|0|65.535|  
|<xref:System.UInt32?displayProperty=fullName>|Sin signo|4|0|4.294.967.295|  
|<xref:System.UInt64?displayProperty=fullName>|Sin signo|8|0|18.446.744.073.709.551.615|  
  
 Cada tipo integral admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita. Cada entero también incluye métodos para realizar comparaciones de igualdad y comparaciones relativas, para convertir la representación de cadena de un número en ese entero y para convertir un entero en su representación de cadena. Algunas operaciones matemáticas adicionales más allá de aquellas controlan los operadores estándares, como el redondeo y la identificación del valor mayor o menor de dos números enteros, están disponibles desde el <xref:System.Math> clase. También puede trabajar con los bits individuales en un valor entero utilizando el <xref:System.BitConverter> clase.  
  
 Tenga en cuenta que los tipos enteros sin signo no son conformes a CLS. Para obtener más información, consulte [independencia del lenguaje y componentes independientes del lenguaje](../../docs/standard/language-independence-and-language-independent-components.md).  
  
## <a name="floating-point-types"></a>Tipos de punto flotante  
 .NET Framework incluye tres tipos primitivos de punto flotante, que se enumeran en la tabla siguiente.  
  
|Tipo|Tamaño (en bytes)|Mínima|Máximo|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=fullName>|8|-1,79769313486232e308|-1,79769313486232e308|  
|<xref:System.Single?displayProperty=fullName>|4|-3,402823e38|-3,402823e38|  
|<xref:System.Decimal?displayProperty=fullName>|16|-79.228.162.514.264.337.593.543.950.335|79.228.162.514.264.337.593.543.950.335|  
  
 Cada tipo de punto flotante admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita. Cada uno incluye también métodos para realizar comparaciones de igualdad y comparaciones relativas, para convertir la representación de cadena de un número de punto flotante y para convertir un número de punto flotante en su representación de cadena. Algunas operaciones matemáticas, algebraicas y trigonométricas adicionales están disponibles en la <xref:System.Math> clase. También puede trabajar con los bits individuales de <xref:System.Double> y <xref:System.Single> valores usando el <xref:System.BitConverter> clase. El <xref:System.Decimal?displayProperty=fullName> estructura tiene sus propios métodos, <xref:System.Decimal.GetBits%2A?displayProperty=fullName> y [Decimal.Decimal (Int32\<xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=fullName>, para trabajar con un valor decimal individual bits, así como su propio conjunto de métodos para realizar algunas operaciones matemáticas adicionales.  
  
 El <xref:System.Double> y <xref:System.Single> tipos están pensados para utilizarse con valores que por su naturaleza, no son precisos (como la distancia entre dos estrellas del sistema solar) y para aplicaciones en el que no se necesita un alto grado de precisión y pequeño error de redondeo. Debe utilizar el <xref:System.Decimal?displayProperty=fullName> tipo para casos en los que la mayor precisión es necesaria y no es deseable, errores de redondeo  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=fullName> es un tipo inmutable que representa un entero arbitrariamente grande cuyo valor en teoría no tiene ningún límite superior o inferior. Los métodos de la <xref:System.Numerics.BigInteger> tipo análogos a los de otros tipos integrales.  
  
## <a name="complex"></a>Complex  
 El <xref:System.Numerics.Complex> tipo representa un número complejo, es decir, un número con un número real y un número imaginario. Admite un conjunto estándar de operadores de aritmética, comparación, igualdad, conversión explícita y conversión implícita, así como métodos matemáticos, algebraicos y trigonométricos.  
  
## <a name="simd-enabled-vector-types"></a>Tipos de vector habilitados para SIMD  
 El <xref:System.Numerics> espacio de nombres incluye un conjunto de tipos de vector habilitados para SIMD para .NET Framework. Las operaciones SIMD (operaciones con múltiples datos y una sola instrucción) permiten ejecuciones en paralelo en el nivel de hardware, obteniendo así grandes mejoras de rendimiento en aplicaciones matemáticas, científicas y de gráficos que realizan cálculos con vectores.  
  
 Los tipos de vector habilitados para  SIMD en .NET Framework incluyen los siguientes:.  Además, System.Numerics.Vectors incluye un tipo Plane y un tipo Quaternion.  
  
-   <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, y <xref:System.Numerics.Vector4> tipos, que son 2, 3 y 4 dimensiones vectores de tipo <xref:System.Single>.  
  
-   Dos tipos de matriz, <xref:System.Numerics.Matrix3x2>, que representa una matriz de 3 x 2; y <xref:System.Numerics.Matrix4x4>, que representa una matriz de 4 x 4.  
  
-   El <xref:System.Numerics.Plane> y <xref:System.Numerics.Quaternion> tipos.  
  
 Los tipos de vector habilitados para SimD se implementan en IL, lo que permite usarlos en compiladores JIY y en hardware no compatible con SimD. Para sacar partido de las instrucciones de SIMD, sus aplicaciones de 64 bits se deben compilar por el nuevo compilador JIT de 64 bits para código administrado, que se incluye con .NET Framework 4.6; agrega compatibilidad con SIMD cuando se destinan a procesadores x64.  
  
 También puede descargar SIMD como un [paquete NuGet](http://www.nuget.org/packages/System.Numerics.Vectors).  El paquete de NuGET también incluye un tipo genérico <xref:System.Numerics.Vector%601> estructura que le permite crear un vector de cualquier tipo numérico primitivo. (Los tipos numéricos primitivos incluyen todos los tipos numéricos en el <xref:System> espacio de nombres excepto <xref:System.Decimal>.) Además, el <xref:System.Numerics.Vector%601> estructura proporciona una biblioteca de métodos útiles que se pueden llamar cuando se trabaja con vectores.  
  
## <a name="see-also"></a>Vea también  
 [Elementos esenciales de aplicaciones](../../docs/standard/application-essentials.md)