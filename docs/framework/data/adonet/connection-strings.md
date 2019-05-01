---
title: Cadenas de conexión de ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1197335f3ba2a09b6e7303d31bc32383d1fd3436
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032770"
---
# <a name="connection-strings-in-adonet"></a>Cadenas de conexión de ADO.NET

Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos. El proveedor de datos recibe la cadena de conexión como el valor de la <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> propiedad. El proveedor analiza la cadena de conexión y se garantiza que la sintaxis es correcta y que se admiten las palabras clave. El <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> método pasa los parámetros de conexión analizado al origen de datos. El origen de datos realiza la validación y establece una conexión.

## <a name="connection-string-syntax"></a>Sintaxis de la cadena de conexión

Una cadena de conexión es una lista delimitada por punto y coma de pares de parámetro de clave/valor:

    keyword1=value; keyword2=value;

Palabras clave no distinguen mayúsculas de minúsculas. Sin embargo, los valores, pueden ser entre mayúsculas y minúsculas, según el origen de datos. Pueden contener las palabras clave y valores [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode). Espacio en blanco inicial y final se omite en las palabras clave y sin comillas los valores.

Si el valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters), o iniciales o finales de espacio en blanco, debe encerrarse entre comillas simples o dobles. Por ejemplo:

    Keyword=" whitespace  ";
    Keyword='special;character';

El carácter envolvente no puede producirse dentro del valor que se agrega. Por lo tanto, un valor que contiene comillas simples puede incluirse únicamente en las comillas dobles y viceversa:

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

Las comillas a sí mismos, así como el signo igual, no requiere la adición, por lo que las siguientes cadenas de conexión son válidas:

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

Dado que cada valor se lee hasta el punto y coma siguiente o al final de cadena, el valor en el último ejemplo es `a=b=c`, y el punto y coma final es opcional.

Todas las cadenas de conexión comparten la misma sintaxis básica que se ha descrito anteriormente. El conjunto de palabras clave reconocidos depende del proveedor, sin embargo y ha evolucionado durante los años desde las primeras API como *ODBC*. El *.NET Framework* proveedor de datos para *SQL Server* (`SqlClient`) es compatible con muchas palabras clave de API anteriores, pero es generalmente más flexible y acepta sinónimos para muchos de la cadena de conexión comunes palabras clave.

Errores de escritura pueden provocar errores. Por ejemplo, `Integrated Security=true` es válido, pero `IntegratedSecurity=true` produce un error.

Las cadenas de conexión creadas manualmente en tiempo de ejecución desde una entrada de usuario son vulnerables a ataques por inyección de cadenas y poner en peligro la seguridad en el origen de datos. Para abordar estos problemas, *ADO.NET* 2.0 introducidas [generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md) para cada *.NET Framework* proveedor de datos. Estos generadores de cadenas de conexión exponen parámetros como propiedades fuertemente tipadas y hacen posible validar la cadena de conexión antes de enviarla al origen de datos.

## <a name="in-this-section"></a>En esta sección

[Generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)\
Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.

[Las cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\
Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.

[Sintaxis de la cadena de conexión](../../../../docs/framework/data/adonet/connection-string-syntax.md)\
Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.

[Protección de la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)\
Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.

## <a name="see-also"></a>Vea también

- [Conexión a un origen de datos](/cpp/data/odbc/connecting-to-a-data-source)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
