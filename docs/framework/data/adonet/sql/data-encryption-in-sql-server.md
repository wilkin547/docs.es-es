---
title: Cifrado de datos en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4ea062a65f250a3532249783b0c7b147ed460317
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="data-encryption-in-sql-server"></a>Cifrado de datos en SQL Server
SQL Server proporciona funciones para cifrar y descifrar datos con un certificado, una clave asimétrica o una clave simétrica. El programa administra estas opciones en un almacén de certificados interno. El almacén usa una jerarquía de cifrado que protege los certificados y las claves en un nivel, con la capa por encima de él en la jerarquía. Esta área de características de SQL Server se denomina almacenamiento secreto.  
  
 El modo más rápido de cifrado que admiten las funciones de cifrado es el cifrado de clave simétrica. Este modo resulta adecuado para controlar grandes volúmenes de datos. Las claves simétricas se pueden cifrar mediante certificados, contraseñas u otras claves simétricas.  
  
## <a name="keys-and-algorithms"></a>Claves y algoritmos  
 SQL Server admite varios algoritmos de cifrado de clave simétrica, incluidos DES, Triple DES, RC2, RC4, RC4 de 128 bits, DESX, AES de 128 bits, AES de 192 bits y AES de 256 bits. Los algoritmos se implementan con la API Windows Crypto.  
  
 En el ámbito de una conexión de base de datos, SQL Server puede mantener varias claves simétricas abiertas. Las claves abiertas se recuperan del almacén y están disponibles para descifrar datos. Cuando se descifra un elemento de datos, no es necesario especificar la clave simétrica que se debe usar. Cada valor cifrado contiene el identificador de clave (GUID de clave) de la clave usada para cifrarlo. Si se descifra la clave correcta y está abierta, el motor crea una correspondencia entre la secuencia de bytes cifrada y la clave simétrica abierta. Esta clave se utiliza para realizar el descifrado y devolver los datos. Si no está abierta la clave correcta, se devuelve NULL.  
  
 Para obtener un ejemplo que muestra cómo trabajar con los datos cifrados en una base de datos, vea [Cómo: cifrar una columna de datos](http://go.microsoft.com/fwlink/?LinkID=128559) en libros en pantalla de SQL Server.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información sobre el cifrado de datos, vea los siguientes recursos.  
  
|||  
|-|-|  
|[Cifrado de SQL Server](http://msdn.microsoft.com/library/bb510663.aspx) en libros en pantalla de SQL Server|Proporciona información general del cifrado en SQL Server. En este tema se incluyen vínculos a temas y temas de procedimientos adicionales.|  
|[Jerarquía de cifrado](http://msdn.microsoft.com/library/ms189586.aspx) y [temas de procedimientos de cifrado](http://msdn.microsoft.com/library/aa337557.aspx) en libros en pantalla de SQL Server|Ofrece información general del cifrado en SQL Server. En este tema se incluyen vínculos a temas y temas de procedimientos adicionales.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Autenticación en SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Roles de servidor y base de datos en SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [Propiedad y separación de esquemas de usuario en SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [Autorización y permisos en SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
