---
title: Procedimiento para asignar jerarquías de herencia
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: c0709fde96a5d2f39f04a08ccd24ddf90c782f30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166422"
---
# <a name="how-to-map-inheritance-hierarchies"></a>Procedimiento para asignar jerarquías de herencia

Para implementar la asignación de herencia en LINQ, debe especificar los atributos y las propiedades de atributo en la clase raíz de la jerarquía de herencia como se describe en los pasos siguientes. Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para asignar jerarquías de herencia. Vea [Cómo: configurar la herencia mediante Object](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)Relational Designer.  
  
> [!NOTE]
> No se requieren atributos o propiedades especiales en las subclases. Observe sobre todo que las subclases no tienen el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>Para asignar una jerarquía de herencia  
  
1. Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la clase raíz.  
  
2. También en la clase raíz, agregue un atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> para cada clase de la estructura jerárquica.  
  
3. Para cada atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, defina una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Esta propiedad contiene un valor que aparece en la tabla de base de datos, en la columna <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>, para indicar a qué clase o subclase pertenece esta fila de datos.  
  
4. Para cada atributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, agregue también una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Esta propiedad contiene un valor que especifica a qué clase o subclases representa el valor de clave.  
  
5. En uno de los atributos <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>, agregue una propiedad <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Esta propiedad sirve para designar una asignación de *reserva* cuando el valor de discriminador de la tabla de base de datos no coincide con ningún <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> valor de las asignaciones de herencia.  
  
6. Agregue una propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> para un atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Esta propiedad indica que ésta es la columna que contiene el valor <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## <a name="example"></a>Ejemplo  
  
> [!NOTE]
> Si usa Visual Studio, puede usar el Object Relational Designer para configurar la herencia. Consulte [Cómo: configurar la herencia mediante Object](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer) Relational Designer  
  
 En el ejemplo de código siguiente, `Vehicle` se define como la clase raíz y se han implementado los pasos anteriores para describir la jerarquía de Linq.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [Compatibilidad de herencia](inheritance-support.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
