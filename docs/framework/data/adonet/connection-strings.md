---
title: Cadenas de conexión
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: cb0b2831a22f3fe51dd7c5bfbe51e72f266a0003
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980241"
---
# <a name="connection-strings-in-adonet"></a>Cadenas de conexión de ADO.NET

Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos. El proveedor de datos recibe la cadena de conexión como el valor de la propiedad <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>. El proveedor analiza la cadena de conexión y garantiza que la sintaxis es correcta y que se admiten las palabras clave. A continuación, el método <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> pasa los parámetros de conexión analizados al origen de datos. El origen de datos realiza una validación adicional y establece una conexión.

## <a name="connection-string-syntax"></a>Sintaxis de cadena de conexión

Una cadena de conexión es una lista delimitada por signos de punto y coma de pares de parámetros de clave-valor:

```csharp
keyword1=value; keyword2=value;
```

Las palabras clave no distinguen mayúsculas de minúsculas. Sin embargo, los valores pueden distinguir entre mayúsculas y minúsculas, en función del origen de datos. Las palabras clave y los valores pueden contener [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode). Los espacios en blanco iniciales y finales se omiten en las palabras clave y los valores sin comillas.

Si un valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters)o espacios en blanco iniciales o finales, debe incluirse entre comillas simples o dobles. Por ejemplo:

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

Es posible que el carácter envolvente no se encuentre dentro del valor que contiene. Por lo tanto, un valor que contenga comillas simples solo se puede incluir entre comillas dobles y viceversa:

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

También puede escapar el carácter envolvente con dos de ellos juntos:

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

Las comillas, así como el signo igual, no requieren caracteres de escape, por lo que las siguientes cadenas de conexión son válidas:

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

Puesto que cada valor se lee hasta el punto y coma siguiente o el final de la cadena, el valor del último ejemplo es `a=b=c`y el punto y coma final es opcional.

Todas las cadenas de conexión comparten la misma sintaxis básica que se ha descrito anteriormente. Sin embargo, el conjunto de palabras clave reconocidas depende del proveedor y ha evolucionado a lo largo de los años desde API anteriores, como *ODBC*. El proveedor de datos de *.NET Framework* para *SQL Server* (`SqlClient`) admite muchas palabras clave de API anteriores, pero suele ser más flexible y acepta sinónimos para muchas de las palabras clave de cadena de conexión comunes.

Los errores tipográficos pueden producir errores. Por ejemplo, `Integrated Security=true` es válido, pero `IntegratedSecurity=true` produce un error.

Las cadenas de conexión construidas manualmente en tiempo de ejecución desde la entrada de usuario no validada son vulnerables a ataques de inyección de cadenas y ponen en peligro la seguridad en el origen de datos. Para solucionar estos problemas, *ADO.NET* 2,0 presentó [generadores de cadenas de conexión](connection-string-builders.md) para cada proveedor de datos *.NET Framework* . Estos generadores de cadenas de conexión exponen parámetros como propiedades fuertemente tipadas y permiten validar la cadena de conexión antes de enviarla al origen de datos.

## <a name="in-this-section"></a>Esta sección

[Generadores de cadenas de conexión](connection-string-builders.md)\
Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.

[Cadenas de conexión y archivos de configuración](connection-strings-and-configuration-files.md)\
Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.

\ de [Sintaxis de cadena de conexión](connection-string-syntax.md)
Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.

[Proteger la información de conexión](protecting-connection-information.md)\
Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.

## <a name="see-also"></a>Vea también

- [Conexión a un origen de datos](/cpp/data/odbc/connecting-to-a-data-source)
- [Información general sobre ADO.NET](ado-net-overview.md)
