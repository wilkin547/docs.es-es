---
title: Procedimiento para ejecutar una consulta polimórfica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545342"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Procedimiento para ejecutar una consulta polimórfica

En este tema se muestra cómo ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta polimórfica mediante el operador de [tipo](./language-reference/oftype-entity-sql.md) .

### <a name="to-run-the-code-in-this-example"></a>Para ejecutar el código de este ejemplo

1. Agregue el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) al proyecto y configure el proyecto para que use el Entity Framework. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Modifique el modelo conceptual para que tenga una herencia de tabla por jerarquía siguiendo los pasos de [Tutorial: asignar la herencia-tabla por jerarquía](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa un operador OFTYPE para obtener y mostrar una colección únicamente de `OnsiteCourses` a partir de una colección de `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Vea también

- [Proveedor de EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
