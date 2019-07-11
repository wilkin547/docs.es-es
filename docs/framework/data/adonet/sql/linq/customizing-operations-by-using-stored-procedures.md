---
title: Personalizar operaciones utilizando procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
ms.openlocfilehash: d9f8d15b46f6e5575bd206bf572ffda0365e58f6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743557"
---
# <a name="customizing-operations-by-using-stored-procedures"></a>Personalizar operaciones utilizando procedimientos almacenados
Los procedimientos almacenados representan un enfoque común para invalidar el comportamiento predeterminado. Los ejemplos de este tema muestran cómo utilizar los contenedores de método generados para los procedimientos almacenados, y cómo se puede llamar directamente a los procedimientos almacenados.  
  
 Si utiliza Visual Studio, puede usar Object Relational Designer para asignar procedimientos almacenados para realizar inserciones, actualizaciones y eliminaciones.  
  
> [!NOTE]
>  Para volver a leer los valores generados por la base de datos, utilice parámetros de salida en los procedimientos almacenados. Si no puede usar los parámetros de salida, escribir invalida la implementación de un método parcial en lugar de depender generado por Object Relational Designer. Los miembros asignados a los valores generados por la base de datos deben establecerse en los valores adecuados una vez que se ha completado correctamente una operación `INSERT` o `UPDATE`. Para obtener más información, consulte [responsabilidades de los desarrolladores invalidar un comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 En el ejemplo siguiente se da por hecho que la clase `Northwind` contiene dos métodos para llamar a los procedimientos almacenados que se utilizan para las invalidaciones en una clase derivada.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 La clase siguiente utiliza estos métodos para la invalidación.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 Puede utilizar `NorthwindThroughSprocs` de la misma forma que utilizaría `Northwnd`.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Responsabilidades del desarrollador al invalidar un comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
