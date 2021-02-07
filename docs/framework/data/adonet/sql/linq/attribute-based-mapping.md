---
description: 'Más información acerca de: asignación de Attribute-Based'
title: Asignación basada en atributos
ms.date: 03/30/2017
ms.assetid: 6dd89999-f415-4d61-b8c8-237d23d7924e
ms.openlocfilehash: 9dfe9fce10d7ba76281afd843385c734e86af245
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712732"
---
# <a name="attribute-based-mapping"></a>Asignación basada en atributos

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna una base de datos SQL Server a un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos aplicando atributos o utilizando un archivo de asignación externo. En este tema se describe el enfoque basado en atributos.  
  
 En su forma más elemental, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna una base de datos a un <xref:System.Data.Linq.DataContext>, una tabla a una clase y las columnas y relaciones a las propiedades de esas clases. También puede utilizar atributos para asignar una jerarquía de herencia en su modelo de objetos. Para obtener más información, vea [Cómo: generar el modelo de objetos en Visual Basic o C#](how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
 Los desarrolladores que usan Visual Studio normalmente realizan la asignación basada en atributos mediante el Object Relational Designer. También puede usar la herramienta de la línea de comandos de SQLMetal o incluir los atributos en el código manualmente. Para obtener más información, vea [Cómo: generar el modelo de objetos en Visual Basic o C#](how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
> [!NOTE]
> También puede realizar la asignación utilizando un archivo XML externo. Para obtener más información, consulte [asignación externa](external-mapping.md).  
  
 En las secciones siguientes se describe con más detalle la asignación basada en atributos. Para obtener más información, vea el espacio de nombres <xref:System.Data.Linq.Mapping>.  
  
## <a name="databaseattribute-attribute"></a>Atributo DatabaseAttribute  

 Utilice este atributo para especificar el nombre predeterminado de la base de datos cuando la conexión no proporciona ningún nombre. Este atributo es opcional, pero, si lo utiliza, debe aplicar la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, como se indica en la tabla siguiente.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|String|Consulta <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.|Cuando se usa con su propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, especifica el nombre de la base de datos.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
## <a name="tableattribute-attribute"></a>Atributo TableAttribute  

 Utilice este atributo para designar una clase como una clase de entidad que está asociada a una tabla o vista de base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] trata las clases que tienen este atributo como clases persistentes. En la tabla siguiente se describe la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>|String|La misma cadena que el nombre de clase|Designa una clase como una clase de entidad que está asociada a una tabla de base de datos.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="columnattribute-attribute"></a>Atributo ColumnAttribute  

 Utilice este atributo para designar un miembro de una clase de entidad para que represente una columna de una tabla de base de datos. Este atributo se puede aplicar cualquier campo o propiedad.  
  
 Solo los miembros que identifique como columnas se recuperarán y conservarán cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] guarde los cambios en la base de datos. Se supone que los miembros que no tienen este atributo no son persistentes y no se envían para operaciones de inserción o actualización.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>|AutoSync|Nunca|Indica a Common Language Runtime (CLR) que recupere el valor después de una operación de inserción o actualización.<br /><br /> Opciones: Always, Never, OnUpdate, OnInsert.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>|Boolean|`true`|Indica que una columna puede contener valores nulos.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>|String|Tipo de columna de base de datos deducido|Utiliza tipos de base de datos y modificadores para especificar el tipo de la columna de base de datos.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>|String|Vacío|Define una columna calculada en una base de datos.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>|Boolean|`false`|Indica que una columna contiene valores que la base de datos genera automáticamente.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>|Boolean|`false`|Indica que la columna contiene un valor de discriminador para una jerarquía de herencia de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>|Boolean|`false`|Especifica que este miembro de clase representa una columna que es o forma parte de las claves principales de la tabla.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>|Boolean|`false`|Identifica el tipo de columna del miembro como una marca de tiempo o número de versión de la base de datos.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>|UpdateCheck|`Always`, a menos que <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> sea `true` para un miembro|Especifica cómo se plantea [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la detección de conflictos de simultaneidad optimista.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
> [!NOTE]
> Los valores de propiedad AssociationAttribute y ColumnAttribute Storage distinguen entre mayúsculas y minúsculas. Por ejemplo, asegúrese de que los valores utilizados en el atributo de la propiedad AssociationAttribute.Storage coinciden con el uso de mayúsculas y minúsculas para los nombres de propiedad correspondientes del resto del código. Esto se aplica a todos los lenguajes de programación de .NET, incluso aquellos que normalmente no distinguen mayúsculas de minúsculas, incluido Visual Basic. Para obtener más información acerca de la propiedad Storage, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="associationattribute-attribute"></a>Atributo AssociationAttribute  

 Utilice este atributo para designar una propiedad que represente una asociación en la base de datos, como una relación entre clave externa y clave principal. Para obtener más información acerca de las relaciones, vea [Cómo: asignar relaciones de base de datos](how-to-map-database-relationships.md).  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteOnNull%2A>|Boolean|`false`|Cuando se coloca en una asociación cuyos miembros de clave externa no aceptan valores Null, elimina el objeto cuando la asociación está establecida en null.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteRule%2A>|String|None|Agrega comportamiento de eliminación a una asociación.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsForeignKey%2A>|Boolean|`false`|Si es verdadero, designa el miembro como la clave externa de una asociación que representa una relación de base de datos.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsUnique%2A>|Boolean|`false`|Si es verdadero, indica una restricción de unicidad en la clave externa.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>|String|Identificador de la clase relacionada|Designa uno o más miembros de la clase de entidad de destino como valores de clave en el otro lado de la asociación.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.ThisKey%2A>|String|Identificador de la clase contenedora|Designa miembros de esta clase de entidad para que representen los valores de clave en este lado de la asociación.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.AssociationAttribute>.  
  
> [!NOTE]
> Los valores de propiedad AssociationAttribute y ColumnAttribute Storage distinguen entre mayúsculas y minúsculas. Por ejemplo, asegúrese de que los valores utilizados en el atributo de la propiedad AssociationAttribute.Storage coinciden con el uso de mayúsculas y minúsculas para los nombres de propiedad correspondientes del resto del código. Esto se aplica a todos los lenguajes de programación de .NET, incluso aquellos que normalmente no distinguen mayúsculas de minúsculas, incluido Visual Basic. Para obtener más información acerca de la propiedad Storage, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="inheritancemappingattribute-attribute"></a>Atributo InheritanceMappingAttribute  

 Utilice este atributo para asignar una jerarquía de herencia.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>|String|Ninguno. El valor debe suministrarse.|Especifica el valor de código del discriminador.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>|Boolean|`false`|Si es verdadero, crea instancias de un objeto de este tipo cuando ningún valor de discriminador del almacén coincide con ninguno de los valores especificados.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>|Tipo|Ninguno. El valor debe suministrarse.|Especifica el tipo de la clase en la jerarquía.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>.  
  
## <a name="functionattribute-attribute"></a>Atributo FunctionAttribute  

 Utilice este atributo para designar un método para representar un procedimiento almacenado o una función definida por el usuario en la base de datos.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>|Boolean|`false`|Si es falso, indica la asignación a un procedimiento almacenado. Si es verdadero, indica la asignación a una función definida por el usuario.|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.Name%2A>|String|La misma cadena que el nombre en la base de datos|Especifica el nombre del procedimiento almacenado o la función definida por el usuario.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.FunctionAttribute>.  
  
## <a name="parameterattribute-attribute"></a>Atributo ParameterAttribute  

 Utilice este atributo para asignar parámetros de entrada en métodos de procedimiento almacenado.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.DbType%2A>|String|None|Especifica el tipo de base de datos.|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.Name%2A>|String|La misma cadena que el nombre del parámetro en la base de datos|Especifica un nombre para el parámetro.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.ParameterAttribute>.  
  
## <a name="resulttypeattribute-attribute"></a>Atributo ResultTypeAttribute  

 Utilice este atributo para especificar un tipo de resultado.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ResultTypeAttribute.Type%2A>|Tipo|(Ninguna)|Se utiliza en los métodos asignados a los procedimientos almacenados que devuelven <xref:System.Data.Linq.IMultipleResults>. Declara las asignaciones de tipos válidas o esperadas para el procedimiento almacenado.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="dataattribute-attribute"></a>Atributo DataAttribute  

 Utilice este atributo para especificar nombres y campos de almacenamiento privados.  
  
 En la tabla siguiente se describen las propiedades de este atributo.  
  
|Propiedad|Tipo|Valor predeterminado|Descripción|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>|String|Igual que el nombre en la base de datos|Especifica el nombre de la tabla, columna, etc.|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>|String|Descriptores de acceso públicos|Especifica el nombre del campo de almacenamiento subyacente.|  
  
 Para obtener más información, vea <xref:System.Data.Linq.Mapping.DataAttribute>.  
  
## <a name="see-also"></a>Vea también

- [Referencia](reference.md)
