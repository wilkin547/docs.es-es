---
title: Cadenas de conexión de ADO.NET
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: b4e057cab4c562fc51893631c35d66409e1c3731
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45583403"
---
# <a name="connection-strings-in-adonet"></a>Cadenas de conexión de ADO.NET
.NET Framework 2.0 incorporó nuevas capacidades para trabajar con cadenas de conexión, incluida la introducción de nuevas palabras clave en las clases generadoras de cadenas de conexión, que facilitan la creación de cadenas de conexión válidas en tiempo de ejecución.  
  
 Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos. La sintaxis depende del proveedor de datos y la cadena de conexión se analiza mientras se intenta abrir una conexión. Los errores de sintaxis generan una excepción en tiempo de ejecución, pero otros errores solo se producen después de que el origen de datos recibe la información de conexión. Una vez validada la cadena de conexión, el origen de datos aplica las opciones especificadas en ella y abre la conexión.  
  
 El formato de una cadena de conexión es una lista de pares de parámetros de clave y valor delimitados por punto y coma:  
  
 `keyword1=value; keyword2=value;`  
  
 Las palabras clave no distinguen entre mayúsculas y minúsculas y los espacios entre los pares clave-valor se omiten. Sin embargo, los valores pueden distinguir entre mayúsculas y minúsculas, en función del origen de datos. Los valores que contengan un punto y coma, caracteres de comilla sencilla o caracteres de comilla doble deben colocarse entre comillas dobles.  
  
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
