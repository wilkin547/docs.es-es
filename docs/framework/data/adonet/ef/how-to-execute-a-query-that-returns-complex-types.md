---
title: 'Cómo: Ejecutar una consulta que devuelve tipos complejos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 013f1980d2ea13927871719aeea293cfce38b4d5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385312"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Cómo: Ejecutar una consulta que devuelve tipos complejos
En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.  
  
### <a name="to-run-the-code-in-this-example"></a>Para ejecutar el código de este ejemplo  
  
1.  Agregar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Haga doble clic en el archivo .edmx para mostrar el modelo en el [ventana Explorador de modelos](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) de Entity Designer. En la superficie de Entity Designer, seleccione el `Email` y `Phone` propiedades de la `Contact` tipo de entidad, a continuación, secundario y seleccione **refactorizar en nuevo tipo complejo**.  
  
4.  Un nuevo tipo complejo con seleccionado `Email` y `Phone` propiedades se agrega a la **Explorador de modelos**. El tipo complejo se asigna un nombre predeterminado: cambie el tipo a `EmailPhone` en el **propiedades** ventana. También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`. Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.  
  
     Para obtener información sobre cómo crear y modificar tipos complejos mediante el Asistente para Entity Data Model, vea [Cómo: refactorizar propiedades existentes en una propiedad de tipo complejo](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) y [Cómo: crear y modificar tipos complejos](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se ejecuta una consulta que devuelve una colección de `Contact` objetos y muestra dos propiedades de la `Contact` objetos: `ContactID` y los valores de la `EmailPhoneComplexType` tipo complejo.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
