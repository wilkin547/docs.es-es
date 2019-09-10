---
title: Procedimiento para ejecutar una consulta que devuelve tipos complejos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b08b220e969ad1c400413978c85b2f107d64a688
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854643"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Procedimiento para ejecutar una consulta que devuelve tipos complejos
En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.  
  
### <a name="to-run-the-code-in-this-example"></a>Para ejecutar el código de este ejemplo  
  
1. Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework. Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Haga doble clic en el archivo. edmx para mostrar el modelo en la [ventana Explorador de modelos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) de Entity Designer. En la superficie de Entity Designer, seleccione `Email` las `Phone` propiedades y del `Contact` tipo de entidad, haga clic con el botón derecho y seleccione **refactorizar en nuevo tipo complejo**.  
  
4. Un nuevo tipo complejo con las propiedades `Email` y `Phone` seleccionadas se agrega al **Explorador de modelos**. Al tipo complejo se le asigna un nombre predeterminado: cambie el nombre del `EmailPhone` tipo a en la ventana **propiedades** . También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`. Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.  
  
     Para obtener información acerca de cómo crear y modificar tipos complejos mediante el Asistente para Entity Data Model [, consulte How to: Refactorice las propiedades existentes en una propiedad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) de tipo complejo y [cómo: Crear y modificar tipos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))complejos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se ejecuta una consulta que devuelve una colección `Contact` de objetos y muestra dos propiedades de `Contact` los objetos `ContactID` : y los valores del `EmailPhoneComplexType` tipo complejo.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
