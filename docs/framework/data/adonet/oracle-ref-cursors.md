---
title: "Cursores REF CURSOR de Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Cursores REF CURSOR de Oracle
El proveedor de datos .NET Framework para Oracle admite el tipo de datos **REF CURSOR** de Oracle.  Cuando utilice el proveedor de datos para trabajar con cursores REF CURSOR de Oracle, debe tener en cuenta los siguientes comportamientos.  
  
> [!NOTE]
>  Algunos de ellos difieren de los del proveedor Microsoft OLE DB para Oracle \(MSDAORA\).  
  
-   Por motivos de rendimiento, el proveedor de datos para Oracle no enlaza automáticamente tipos de datos **REF CURSOR**, como hace MSDAORA, a menos que los especifique de forma explícita.  
  
-   El proveedor de datos no admite ninguna secuencia de escape ODBC, lo que incluye el escape {resultset} usado para especificar parámetros REF CURSOR.  
  
-   Para ejecutar un procedimiento almacenado que devuelva cursores REF CURSOR, debe definir los parámetros en la <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> de **Cursor** y una <xref:System.Data.OracleClient.OracleParameter.Direction%2A> de **Output**.  El proveedor de datos admite el enlace de cursores REF CURSOR sólo como parámetros de salida;  no los admite como parámetros de entrada.  
  
-   No se permite la obtención de un <xref:System.Data.OracleClient.OracleDataReader> del valor del parámetro.  Los valores son del tipo <xref:System.DBNull> después de la ejecución del comando.  
  
-   El único valor de enumeración **CommandBehavior** que funciona con los cursores REF CURSOR \(por ejemplo, al llamar a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>\) es **CloseConnection**; todos los demás se omiten.  
  
-   El orden de los cursores REF CURSOR en el **OracleDataReader** depende del orden de los parámetros en la **OracleParameterCollection**.  Se omite la propiedad <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>.  
  
-   No se admite el tipo de datos **TABLE** de PL\/SQL.  No obstante, los cursores REF CURSOR resultan más eficientes.  Si tiene que utilizar un tipo de datos **TABLE**, emplee el proveedor de datos OLE DB .NET con MSDAORA.  
  
## En esta sección  
 [Ejemplos de cursores REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Contiene tres ejemplos en los que se muestra el uso de cursores REF CURSOR.  
  
 [Parámetros REF CURSOR en un OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL\/SQL que devuelve un parámetro REF CURSOR y lee el valor como un **OracleDataReader**.  
  
 [Recuperación de datos de varios cursores REF CURSOR mediante un OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL\/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante un **OracleDataReader**.  
  
 [Rellenar un conjunto de datos utilizando uno o varios parámetros REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL\/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.  
  
## Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)