---
title: "Utilizar comandos para modificar datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Utilizar comandos para modificar datos
Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo.  Estos comandos no devuelven filas de la forma en que lo haría una consulta y, en consecuencia, el objeto **Command** proporciona un método **ExecuteNonQuery** para procesarlos.  
  
 Además de utilizar **ExecuteNonQuery** para modificar esquemas, este método se puede usar también para procesar instrucciones SQL que modifican datos sin devolver ninguna fila, como INSERT, UPDATE y DELETE.  
  
 Aunque el método **ExecuteNonQuery** no devuelve ninguna fila, mediante la colección **Parameters** del objeto **Command** se pueden pasar y devolver parámetros de entrada y de salida, así como valores devueltos.  
  
## En esta sección  
 [Actualizar datos en un origen de datos](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.  
  
 [Realizar operaciones de catálogo](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.  
  
## Vea también  
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)