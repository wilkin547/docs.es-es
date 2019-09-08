---
title: Usar comandos para modificar datos
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780557"
---
# <a name="using-commands-to-modify-data"></a>Usar comandos para modificar datos
Mediante un proveedor de datos .NET Framework puede ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos, como CREATE TABLE y ALTER COLUMN, para manipular los esquemas de una base de datos o catálogo. Estos comandos no devuelven filas como lo haría una consulta, por lo que el objeto de **comando** proporciona un **ExecuteNonQuery** para procesarlos.  
  
 Además de usar **ExecuteNonQuery** para modificar el esquema, también puede utilizar este método para procesar instrucciones SQL que modifican datos pero que no devuelven filas, como INSERT, Update y DELETE.  
  
 Aunque el método **ExecuteNonQuery** no devuelve las filas, los parámetros de entrada y salida y los valores devueltos se pueden pasar y devolver a través de la colección **Parameters** del objeto **Command** .  
  
## <a name="in-this-section"></a>En esta sección  
 [Actualización de datos de un origen de datos](updating-data-in-a-data-source.md)  
 Describe la forma de ejecutar comandos o procedimientos almacenados que modifican datos en una base de datos.  
  
 [Realización de operaciones de catálogo](performing-catalog-operations.md)  
 Describe la forma de ejecutar comandos que modifican esquemas de la base de datos.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
