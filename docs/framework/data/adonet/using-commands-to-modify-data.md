---
title: Usar comandos para modificar datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 70a83453eef990a03515a4860917f3c4d72599c3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="using-commands-to-modify-data"></a>Usar comandos para modificar datos
Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo. Estos comandos no devuelven filas tal y como haría una consulta y, por lo que la **comando** objeto proporciona un **ExecuteNonQuery** para procesarlos.  
  
 Además de usar **ExecuteNonQuery** para modificar el esquema, también puede utilizar este método para procesar instrucciones SQL que modifican datos sin que no devuelven filas, como INSERT, UPDATE y DELETE.  
  
 Aunque no se devuelven filas por la **ExecuteNonQuery** parámetros de entrada y salida de método y valores devueltos pueden pasar y devolver a través de la **parámetros** colección de la **comando**  objeto.  
  
## <a name="in-this-section"></a>En esta sección  
 [Actualización de datos de un origen de datos](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.  
  
 [Realización de operaciones de catálogo](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
