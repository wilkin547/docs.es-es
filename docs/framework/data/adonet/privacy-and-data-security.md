---
title: Privacidad y seguridad de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46fa5839-adf7-4c7c-bce3-71e941fa7de9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4109c15e5c1eaf843d57e10e636fa01555083e49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="privacy-and-data-security"></a>Privacidad y seguridad de datos
La protección y la administración de información confidencial en una aplicación de ADO.NET depende de los productos y las tecnologías utilizados para crearla. ADO.NET no proporciona de forma directa servicios para proteger ni cifrar datos.  
  
## <a name="cryptography-and-hash-codes"></a>Criptografía y códigos hash  
 Las clases del espacio de nombres <xref:System.Security.Cryptography> de .NET Framework se pueden utilizar desde las aplicaciones de ADO.NET para impedir que terceras partes no autorizadas lean o modifiquen los datos. Algunas clases son contenedores para Microsoft CryptoAPI no administrado, mientras que otras son implementaciones administradas. El [servicios criptográficos](http://msdn.microsoft.com/en-us/68a1e844-c63c-44af-9247-f6716eb23781) tema se proporciona información general sobre la criptografía en .NET Framework, se describe cómo se implementa la criptografía y cómo realizar tareas criptográficas específicas.  
  
 Al contrario que la criptografía, que permite cifrar datos y descifrarlos posteriormente, el proceso hash de datos es unidireccional. La utilización de algoritmos hash en los datos resulta útil para evitar la manipulación mediante la comprobación de que los datos no han sido alterados: para cadenas de entrada idénticas, los algoritmos hash siempre generan valores de salida cortos idénticos que se pueden comparar fácilmente. [Asegurar la integridad de datos mediante códigos Hash](../../../../docs/standard/security/ensuring-data-integrity-with-hash-codes.md) describe cómo generar y comprobar los valores de hash.  
  
## <a name="encrypting-configuration-files"></a>Cifrar archivos de configuración  
 La protección del acceso al origen de datos es uno de los objetivos más importantes a la hora de proteger una aplicación. Las cadenas de conexión presentan una posible vulnerabilidad si no se protegen. Las cadenas de conexión que se guardan en los archivos de configuración se almacenan en archivos XML estándar para los que .NET Framework ha definido un conjunto común de elementos. La configuración protegida permite cifrar información confidencial en un archivo de configuración. Si bien se ha diseñado principalmente para aplicaciones ASP.NET, la configuración protegida también se puede usar para cifrar secciones del archivo de configuración en aplicaciones Windows. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="securing-string-values-in-memory"></a>Proteger valores de cadena en memoria  
 Si un objeto <xref:System.String> contiene información confidencial, como una contraseña, un número de tarjeta de crédito o datos personales, existe el riesgo de que la información se pueda revelar una vez utilizada, porque la aplicación no puede eliminar los datos de la memoria del equipo.  
  
 Un objeto <xref:System.String> es inmutable, porque no se puede modificar su valor una vez que se ha creado. Los cambios que parecen modificar el valor de la cadena crean de hecho una nueva instancia de un objeto <xref:System.String> en memoria, que almacena los datos como texto sin formato. Además, no es posible predecir si las instancias de cadena se eliminarán de la memoria. La reclamación de memoria con cadenas no es determinista en la recolección de elementos no utilizados de .NET. Debe evitar el uso de las clases <xref:System.String> y <xref:System.Text.StringBuilder> si los datos son realmente confidenciales.  
  
 La clase <xref:System.Security.SecureString> proporciona métodos para cifrar texto con la API de protección de datos (DPAPI) en memoria. La cadena se elimina posteriormente de la memoria cuando ya no es necesaria. No existe ningún método `ToString` para leer rápidamente el contenido de un objeto <xref:System.Security.SecureString>. Puede inicializar una nueva instancia de `SecureString` sin ningún valor o pasándole un nuevo puntero a una matriz de objetos <xref:System.Char>. A continuación, puede usar los diferentes métodos de la clase para trabajar con la cadena. Para obtener más información, descargue el [ejemplo SecureString Application](http://go.microsoft.com/fwlink/?LinkId=120418), que muestra cómo utilizar el `SecureString` de la clase.  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Seguridad de SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
