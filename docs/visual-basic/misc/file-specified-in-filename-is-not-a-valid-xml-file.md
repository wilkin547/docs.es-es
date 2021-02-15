---
description: 'Más información acerca de: el archivo especificado en FileName no es un archivo XML válido'
title: El archivo especificado en Nombre de archivo no es un archivo XML válido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: c7d521986f3489345117a3947ed1e9b459af897e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472987"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>El archivo especificado en Nombre de archivo no es un archivo XML válido

El nombre de archivo proporcionado no es un archivo XML válido. Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD). Los esquemas XSD son el método preferido para especificar gramáticas XML en el .NET Framework.

> [!NOTE]
> En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML. El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML. Sin embargo, en Visual Studio 2012, el diseñador para crear y editar conjuntos de objetos con tipo es el **Diseñador de DataSet**. Para obtener más información, vea [crear y editar conjuntos de datos con tipo](/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe que está proporcionando el nombre de archivo correcto.

- Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**. En el menú **XML** , haga clic en **Validar datos XML**. Los errores se muestran en la ventana **Lista de tareas**.

- Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.

## <a name="see-also"></a>Consulte también

- <xref:System.Xml>
- [Procedimiento para analizar rutas de acceso a archivos](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
