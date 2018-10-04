---
title: Cadenas de conexión de ADO.NET
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1e6e2b6870195c99279639e1f4576a30b7126d4d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583701"
---
# <a name="connection-strings-in-adonet"></a>Cadenas de conexión de ADO.NET
.NET Framework 2.0 incorporó nuevas capacidades para trabajar con cadenas de conexión, incluida la introducción de nuevas palabras clave en las clases generadoras de cadenas de conexión, que facilitan la creación de cadenas de conexión válidas en tiempo de ejecución.  
  
Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos. La sintaxis depende del proveedor de datos y la cadena de conexión se analiza mientras se intenta abrir una conexión. Los errores de sintaxis generan una excepción en tiempo de ejecución, pero otros errores solo se producen después de que el origen de datos recibe la información de conexión. Una vez validada la cadena de conexión, el origen de datos aplica las opciones especificadas en ella y abre la conexión.
  
El formato de una cadena de conexión es una lista de pares de parámetros de clave y valor delimitados por punto y coma:
  
    keyword1=value; keyword2=value;
  
Palabras clave no distinguen mayúsculas de minúsculas. Sin embargo, los valores, pueden ser entre mayúsculas y minúsculas, según el origen de datos. Pueden contener las palabras clave y valores [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode), aunque iniciales y finales de espacio en blanco se omite en las palabras clave y sin comillas los valores.

Si el valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters), iniciales o finales de espacio en blanco debe incluirse entre comillas simples o dobles, p. ej.:

    Keyword=" whitespace  ";
    Keyword='special;character';

El carácter envolvente no puede producirse dentro del valor que se agrega. Por lo tanto, un valor que contiene comillas simples puede incluirse únicamente en las comillas dobles y viceversa:

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

Las comillas a sí mismos, así como el signo igual, no requiere la adición, por lo que las siguientes cadenas de conexión son válidas:

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

Dado que cada valor se lee hasta el punto y coma siguiente o al final de cadena, el valor en el último ejemplo es `a=b=c`, y el punto y coma final es opcional.

La sintaxis válida de cadena de conexión depende del proveedor y ha evolucionado a lo largo de los años desde las primeras API como ODBC. El proveedor de datos .NET Framework para SQL Server (SqlClient) incorpora muchos elementos de la sintaxis antigua y, por lo general, es más flexible con la sintaxis común de cadena de conexión. Con frecuencia existen sinónimos igualmente válidos para los elementos de sintaxis de la cadena de conexión, pero algunos errores de sintaxis y ortografía pueden generar problemas. Por ejemplo, "`Integrated Security=true`" es válido, en tanto que "`IntegratedSecurity=true`" genera un error. Además, las cadenas de conexión construidas en tiempo de ejecución a partir de entrada de usuario no validada pueden dar lugar a ataques de inyección de cadenas, lo que pone en peligro la seguridad en el origen de datos.
  
Para solucionar estos problemas, ADO.NET 2.0 incorporó nuevos generadores de cadenas de conexión para cada proveedor de datos .NET Framework. Las palabras clave se exponen como propiedades, lo que permite validar la sintaxis de la cadena de conexión antes de su envío al origen de datos.
  
## <a name="in-this-section"></a>En esta sección  
 [Generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.
  
 [Cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.
  
 [Sintaxis de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.
  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.
  
## <a name="see-also"></a>Vea también  
 [Conexión a un origen de datos](/cpp/data/odbc/connecting-to-a-data-source)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
