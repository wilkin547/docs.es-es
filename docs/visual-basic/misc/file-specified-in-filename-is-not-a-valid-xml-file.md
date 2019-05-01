---
title: El archivo especificado en Nombre de archivo no es un archivo XML válido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 89499b07e767bd0b3a777db4e5155f64a4357f0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052318"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>El archivo especificado en Nombre de archivo no es un archivo XML válido

El nombre de archivo proporcionado no es un archivo XML válido. Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD). Los esquemas XSD son el método preferido para especificar gramáticas XML en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].

> [!NOTE]
> En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML. El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML. Sin embargo, en Visual Studio 2012, el diseñador para crear y editar conjuntos de datos con tipo es el **Diseñador de Dataset**. Para obtener más información, consulte [crear y editar conjuntos de datos con tipo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe que está proporcionando el nombre de archivo correcto.

- Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**. En el menú **XML** , haga clic en **Validar datos XML**. Los errores se muestran en la ventana **Lista de tareas**.

- Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.

## <a name="see-also"></a>Vea también

- <xref:System.Xml>
- [Cómo: Analizar rutas de acceso a archivos](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)