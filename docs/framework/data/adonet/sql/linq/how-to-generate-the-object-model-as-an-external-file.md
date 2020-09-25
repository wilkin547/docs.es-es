---
title: Procedimiento para generar el modelo de objetos como un archivo externo
ms.date: 03/30/2017
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
ms.openlocfilehash: 2442caec5400759ae2bfeca35f99ebd2ff52d011
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180769"
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a>Procedimiento para generar el modelo de objetos como un archivo externo

Como alternativa a la asignación basada en atributos, puede generar su modelo de objetos como un archivo XML externo mediante la herramienta de línea de comandos SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md). Utilizando un archivo de asignación XML externo, se reduce el desorden en su código. También puede cambiar el comportamiento modificando el archivo externo sin recompilar los binarios de su aplicación. Para obtener más información, consulte [asignación externa](external-mapping.md).  
  
> [!NOTE]
> La Object Relational Designer no admite la generación de un archivo de asignación externo.  
  
## <a name="example"></a>Ejemplo  

 El comando siguiente genera un archivo de asignación externo a partir de la base de datos de ejemplo Northwind.  
  
```console  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a>Ejemplo  

 El siguiente fragmento de un archivo de asignación externo muestra la asignación para la tabla Clientes de la base de datos de ejemplo Northwind. Este fragmento se generó ejecutando SQLMetal con la opción **/map** .  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>Consulte también

- [Crear el modelo de objetos](creating-the-object-model.md)
- [Asignación externa](external-mapping.md)
- [Cómo: Generación del modelo de objetos en Visual Basic o C#](how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
