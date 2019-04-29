---
title: Parámetros REF CURSOR de Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: b23b0f07d7755fed820481a3ad1fe831ae3f5224
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771865"
---
# <a name="oracle-ref-cursors"></a>Parámetros REF CURSOR de Oracle
El proveedor de datos de .NET Framework para Oracle admite Oracle **REF CURSOR** tipo de datos. Cuando utilice el proveedor de datos para trabajar con cursores REF CURSOR de Oracle, debe tener en cuenta los siguientes comportamientos.  
  
> [!NOTE]
>  Algunos de ellos difieren de los del proveedor Microsoft OLE DB para Oracle (MSDAORA).  
  
- Por motivos de rendimiento, el proveedor de datos para Oracle no enlaza automáticamente **REF CURSOR** tipos de datos, como hace MSDAORA, a menos que especifique explícitamente.  
  
- El proveedor de datos no admite ninguna secuencia de escape ODBC, lo que incluye el escape {resultset} usado para especificar parámetros REF CURSOR.  
  
- Para ejecutar un procedimiento almacenado que devuelva cursores REF CURSOR, debe definir los parámetros en el <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> de **Cursor** y un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> de **salida**. El proveedor de datos admite el enlace de cursores REF CURSOR sólo como parámetros de salida; no los admite como parámetros de entrada.  
  
- No se permite la obtención de un <xref:System.Data.OracleClient.OracleDataReader> del valor del parámetro. Los valores son del tipo <xref:System.DBNull> después de la ejecución del comando.  
  
- La única **CommandBehavior** valor de enumeración que funciona con cursores REF cursor (por ejemplo, al llamar a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) es **CloseConnection**; se omiten todos los demás.  
  
- El orden de los cursores REF cursor en el **OracleDataReader** depende del orden de los parámetros en el **OracleParameterCollection**. Se omite la propiedad <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>.  
  
- PL/SQL **tabla** no se admite el tipo de datos. No obstante, los cursores REF CURSOR resultan más eficientes. Si debe utilizar un **tabla** tipo de datos, utilice el proveedor de datos OLE DB .NET con MSDAORA.  
  
## <a name="in-this-section"></a>En esta sección  
 [Ejemplos de REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Contiene tres ejemplos en los que se muestra el uso de cursores REF CURSOR.  
  
 [Parámetros REF CURSOR en un objeto OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un **OracleDataReader**.  
  
 [Recuperación de datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante una **OracleDataReader**.  
  
 [Relleno de un conjunto de datos utilizando uno o varios parámetros REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
