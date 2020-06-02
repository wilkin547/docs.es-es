---
title: Objetos DataSet, DataTable y DataView
description: Aprenda varias maneras de trabajar con un conjunto de datos de ADO.NET, una representación residente en memoria de los datos que proporciona un modelo de programación relacional coherente.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: f6562452261cbc1f7ee36fb264b858646a42e4f5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286900"
---
# <a name="datasets-datatables-and-dataviews"></a>Objetos DataSet, DataTable y DataView
El <xref:System.Data.DataSet> de ADO.NET es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene. Un <xref:System.Data.DataSet> representa un conjunto completo de datos, incluyendo las tablas que contienen, ordenan y restringen los datos, así como las relaciones entre las tablas.  
  
 Hay varias maneras de trabajar con un <xref:System.Data.DataSet>, que se pueden aplicar de forma independiente o conjuntamente. Puede:  
  
- Crear mediante programación una <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> y una <xref:System.Data.Constraint> en un <xref:System.Data.DataSet> y rellenar las tablas con datos.  
  
- Llenar el <xref:System.Data.DataSet> con tablas de datos de un origen de datos relacional existente mediante `DataAdapter`.  
  
- Cargar y hacer persistente el contenido de <xref:System.Data.DataSet> mediante XML. Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
 También se puede transportar un <xref:System.Data.DataSet> fuertemente tipado mediante un servicio Web XML. El diseño del <xref:System.Data.DataSet> lo convierte en idóneo para el transporte de datos mediante servicios Web XML. Para obtener información general sobre servicios Web XML, vea [Información general de servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)). Para obtener un ejemplo sobre cómo usar un objeto <xref:System.Data.DataSet> desde un servicio Web XML, vea [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md) (Usar un conjunto de datos desde un servicio Web XML).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un conjunto de DataSet](creating-a-dataset.md)  
 Describe la sintaxis para crear una instancia de <xref:System.Data.DataSet>.  
  
 [Agregar un objeto DataTable a un objeto DataSet](adding-a-datatable-to-a-dataset.md)  
 Describe cómo crear tablas y columnas y cómo agregarlas a un <xref:System.Data.DataSet>.  
  
 [Agregar objetos DataRelation](adding-datarelations.md)  
 Describe cómo se crean las relaciones entre tablas en un <xref:System.Data.DataSet>.  
  
 [Navegar por objetos DataRelation](navigating-datarelations.md)  
 Describe cómo se utilizan las relaciones entre tablas en un <xref:System.Data.DataSet> para devolver la filas secundarias o primarias de una relación primaria-secundaria.  
  
 [Combinar contenido de DataSet](merging-dataset-contents.md)  
 Describe cómo se fusiona mediante combinación el contenido de una matriz de <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> con otro <xref:System.Data.DataSet>.  
  
 [Copiar el contenido de DataSet](copying-dataset-contents.md)  
 Describe cómo se crea una copia de un <xref:System.Data.DataSet> que puede contener datos de esquema y datos especificados.  
  
 [Controlar eventos de DataSet](handling-dataset-events.md)  
 Describe los eventos de un <xref:System.Data.DataSet> y cómo utilizarlos.  
  
 [Objetos DataSet con tipo](typed-datasets.md)  
 Explica lo que es un <xref:System.Data.DataSet> con información de tipos y cómo crearlo y utilizarlo.  
  
 [Objetos DataTable](datatables.md)  
 Describe cómo se crea una <xref:System.Data.DataTable>, cómo se define el esquema y cómo se manipulan los datos.  
  
 [Objetos DataTableReader](datatablereaders.md)  
 Describe cómo crear y utilizar un objeto <xref:System.Data.DataTableReader>.  
  
 [Objetos DataView](dataviews.md)  
 Describe cómo se crean `DataViews` y cómo se trabaja con ellas, así como con eventos <xref:System.Data.DataView>.  
  
 [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)  
 Describe cómo interactúa el <xref:System.Data.DataSet> con XML como origen de datos, incluyendo cómo cargar y hacer persistente el contenido de un <xref:System.Data.DataSet> como datos XML.  
  
 [Utilizar un conjunto de datos desde un servicio Web XML](consuming-a-dataset-from-an-xml-web-service.md)  
 Describe cómo crear un servicio Web XML que utilice un <xref:System.Data.DataSet> para transportar los datos.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Novedades de ADO.NET](../whats-new.md)  
 Presenta características nuevas en ADO.NET.  
  
 [Información general de ADO.NET](../ado-net-overview.md)  
 Proporciona una introducción al diseño y a los componentes de ADO.NET.  
  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)  
 Describe cómo se carga un objeto **DataSet** con datos desde un origen de datos.  
  
 [Actualizar orígenes de datos con objetos DataAdapter](../updating-data-sources-with-dataadapters.md)  
 Describe cómo se resuelven los cambios relacionados con los datos de un **DataSet** en el origen de datos.  
  
 [Agregar restricciones existentes a un conjunto de datos](../adding-existing-constraints-to-a-dataset.md)  
 Describe cómo se rellena un objeto **DataSet** con información de clave principal de un origen de datos.  
  
## <a name="see-also"></a>Consulte también

- [ADO.NET](../index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
