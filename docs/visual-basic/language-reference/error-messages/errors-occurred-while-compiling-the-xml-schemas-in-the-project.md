---
description: 'Más información acerca de: BC36810: se produjeron errores al compilar los esquemas XML en el proyecto'
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 78e88208c0d3df12e7bad8ab46b1d91bce559923
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796488"
---
# <a name="bc36810-errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>BC36810: se produjeron errores al compilar los esquemas XML en el proyecto

Se produjeron errores al compilar los esquemas XML en el proyecto. Por ello, XML IntelliSense no está disponible.

 Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto. Este error se produce cuando se agrega un archivo de esquema XSD (. xsd) que entra en conflicto con el conjunto de esquemas XSD existente para el proyecto.

 **Identificador de error:** BC36810

## <a name="to-correct-this-error"></a>Para corregir este error

- Haga doble clic en la advertencia en la ventana **lista de errores** . Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia. Corrija el error en el esquema XSD.

- Asegúrese de que todos los archivos de esquema XSD (. xsd) necesarios se incluyen en el proyecto. Es posible que tenga que hacer clic en **Mostrar todos los archivos** en el menú **proyecto** para ver los archivos. xsd en **Explorador de soluciones**. Haga clic con el botón secundario en un archivo. xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.

- Si usa el Asistente de XML a esquema, este error puede producirse si se infieren esquemas más de una vez desde el mismo origen. En este caso, puede quitar los archivos de esquema XSD existentes del proyecto, agregar un nuevo XML a la plantilla de elemento de esquema y, a continuación, proporcionar el Asistente de XML a esquema con todos los orígenes XML aplicables para el proyecto.

- Si no se identifica ningún error en el esquema XSD, es posible que el compilador XML no tenga suficiente información para proporcionar un mensaje de error detallado. Es posible que pueda obtener información más detallada del error si se asegura de que los espacios de nombres XML para los archivos. xsd incluidos en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML establecido en Visual Studio.

## <a name="see-also"></a>Vea también

- [Lista de errores ventana](/visualstudio/ide/reference/error-list-window)
- [XML](../../programming-guide/language-features/xml/index.md)
