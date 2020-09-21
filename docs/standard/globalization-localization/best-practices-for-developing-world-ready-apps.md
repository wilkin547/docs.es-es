---
title: Prácticas recomendadas para desarrollar aplicaciones de uso internacional
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- global applications, best practices
- world-ready applications, best practices
- globalization [.NET Framework], best practices
- international applications [.NET Framework], best practices
ms.assetid: f08169c7-aad8-4ec3-9a21-9ebd3b89986c
ms.openlocfilehash: 9d9f6b3540bb04dd4af154fce2f91a3a7b6395ba
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555541"
---
# <a name="best-practices-for-developing-world-ready-applications"></a>Prácticas recomendadas para desarrollar aplicaciones de uso internacional

En esta sección se describen las procedimientos recomendados que hay que seguir al desarrollar aplicaciones de uso internacional.

## <a name="globalization-best-practices"></a>Prácticas recomendadas de globalización

1. Haga que la aplicación sea Unicode internamente.

2. Utilice las clases que tienen en cuenta la referencia cultural proporcionadas por el espacio de nombres <xref:System.Globalization> para manipular y aplicar formato a los datos.

    - Para ordenar, utilice las clases <xref:System.Globalization.SortKey> y <xref:System.Globalization.CompareInfo>.

    - Para las comparaciones de cadenas, utilice la clase <xref:System.Globalization.CompareInfo>.

    - Para el formato de fecha y hora, utilice la clase <xref:System.Globalization.DateTimeFormatInfo>.

    - Para aplicar formato numérico, utilice la clase<xref:System.Globalization.NumberFormatInfo>.

    - Para los calendarios gregorianos y los no gregorianos, use la clase <xref:System.Globalization.Calendar> o alguna de las implementaciones de calendario específicas.

3. Utilice las configuraciones de propiedades de las referencias culturales proporcionadas por la clase <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> en las situaciones apropiadas. Utilice la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> para tareas de aplicación de formato, como aplicar formato de fecha y hora, o formato numérico. Para recuperar recursos, utilice la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>. Tenga en cuenta que las propiedades `CurrentCulture` y `CurrentUICulture` se pueden establecer para cada subproceso.

4. Habilite la aplicación para que lea y escriba datos a y desde diversas codificaciones mediante las clases de codificación del espacio de nombres <xref:System.Text>. No suponga que los datos son ASCII. Dé por supuesto que se proporcionarán caracteres internacionales en cualquier parte donde el usuario pueda especificar texto. Por ejemplo, la aplicación debe aceptar caracteres internacionales en los nombres de servidores, directorios, nombres de archivo, nombres de usuario y direcciones URL.

5. Cuando use la clase <xref:System.Text.UTF8Encoding>, por razones de seguridad, utilice la característica de detección de errores que ofrece esta clase. Para activar esta característica, cree una instancia de la clase mediante un constructor que tome el parámetro `throwOnInvalidBytes` y establezca su valor en `true`.

6. Cuando sea posible, trate las cadenas como cadenas enteras en lugar de como una serie de caracteres individuales. Esto es especialmente importante al ordenar o buscar subcadenas. De esta forma evitará problemas asociados con el análisis de caracteres combinados. También puede trabajar con unidades de texto en lugar de caracteres individuales mediante la clase <xref:System.Globalization.StringInfo?displayProperty=nameWithType>.

7. Muestre texto utilizando las clases proporcionadas por el espacio de nombres <xref:System.Drawing>.

8. Por coherencia entre los sistemas operativos, no permita que la configuración de usuario invalide <xref:System.Globalization.CultureInfo>. Use el constructor `CultureInfo` que acepte un parámetro `useUserOverride` y establezca su valor en `false`.

9. Pruebe la funcionalidad de la aplicación en versiones internacionales del sistema operativo usando datos internacionales.

10. Si una decisión en materia de seguridad se basa en el resultado de una comparación de cadenas o un cambio en el uso de mayúsculas y minúsculas, use una operación de cadenas que no tenga en cuenta la referencia cultural. De este modo, se garantiza que el resultado no se ve afectado por el valor de `CultureInfo.CurrentCulture`. Vea la sección [Comparaciones de cadenas que usan la referencia cultural actual](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) de [Prácticas recomendadas para utilizar las cadenas](../base-types/best-practices-strings.md) para obtener un ejemplo de cómo las comparaciones de cadenas que tienen en cuenta la referencia cultural pueden generar resultados incoherentes.

## <a name="localization-best-practices"></a>Prácticas recomendadas de localización

1. Traslade todos los recursos localizables a archivos DLL independientes que sean sólo de recursos. Entre los recursos localizables se incluyen los elementos de la interfaz de usuario, como cadenas, mensajes de error, cuadros de diálogo, menús y recursos de objetos incrustados.

2. No incluya en el código no modificable las cadenas o recursos de la interfaz de usuario.

3. No incluya recursos no localizables en archivos DLL que sean sólo de recursos. Esto produce confusión en los traductores.

4. No utilice cadenas compuestas que se compilan en tiempo de ejecución a partir de frases concatenadas. La localización de las cadenas compuestas resulta difícil porque a menudo se da por supuesto un orden gramatical inglés que no se aplica a todos los idiomas.

5. Evite construcciones ambiguas, como "Empty Folder", donde las cadenas se pueden traducir de forma diferente según los roles gramaticales de los componentes de las cadenas. Por ejemplo, "empty" puede ser tanto un verbo como un adjetivo, lo cual puede conducir a traducciones diferentes en idiomas como el italiano o el francés.

6. Evite utilizar en la aplicación imágenes e iconos que contengan texto. Su localización es costosa.

7. Prevea mucho espacio para expandir la longitud de las cadenas en la interfaz de usuario. En algunos idiomas, las frases pueden requerir entre un 50 y un 75 por ciento más de espacio que en otros idiomas.

8. Utilice la clase <xref:System.Resources.ResourceManager?displayProperty=nameWithType> para recuperar recursos en función de la referencia cultural.

9. Use [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) para crear cuadros de diálogo de Windows Forms, de manera que se puedan localizar mediante el [Editor de recursos de Windows Forms (Winres.exe)](../../framework/tools/winres-exe-windows-forms-resource-editor.md). No programe los cuadros de diálogo de Windows Forms manualmente.

10. Organice una localización profesional (traducción).

11. Para obtener una descripción completa de cómo crear y adaptar los recursos, vea [Recursos en aplicaciones](../../framework/resources/index.md).

## <a name="globalization-best-practices-for-aspnet-applications"></a>Prácticas recomendadas de globalización para aplicaciones de ASP.NET

1. Establezca explícitamente las propiedades <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> y <xref:System.Globalization.CultureInfo.CurrentCulture%2A> en su aplicación. No se base en valores predeterminados.

2. Tenga en cuenta que las aplicaciones de ASP.NET son administradas y, por lo tanto, pueden utilizar las mismas clases que otras aplicaciones administradas para recuperar, mostrar y tratar información basada en la referencia cultural.

3. Tenga presente que puede especificar los tres tipos siguientes de codificación en ASP.NET:

    - requestEncoding especifica la codificación que se recibe desde el explorador del cliente.

    - responseEncoding especifica la codificación que se envía al explorador del cliente. En la mayoría de los casos, esta codificación debe ser igual que la especificada para requestEncoding.

    - fileEncoding especifica la codificación predeterminada para el análisis de archivos .aspx, .asmx y .asax.

4. Especifique los valores de los atributos requestEncoding, responseEncoding, fileEncoding, culture y uiCulture en las tres ubicaciones siguientes de una aplicación ASP.NET:

    - En la sección de globalización de un archivo Web.config. Este archivo es externo a la aplicación de ASP.NET. Para obtener más información, consulte [Elemento \<globalization>](/previous-versions/dotnet/netframework-4.0/hy4kkhe0(v=vs.100)).

    - En una directiva de página. Tenga en cuenta que, cuando una aplicación está en una página, el archivo ya se ha leído. Por lo tanto, es demasiado tarde para especificar fileEncoding y requestEncoding. Sólo uiCulture, Culture y responseEncoding se pueden especificar en una directiva de página.

    - Mediante programación en el código de la aplicación. Esta configuración puede cambiarse para cada solicitud. Como con la directiva de página, cuando se llega al código de la aplicación es demasiado tarde para especificar fileEncoding y requestEncoding. Sólo uiCulture, Culture y responseEncoding se pueden especificar en el código de la aplicación.

5. Tenga en cuenta que el valor de uiCulture puede establecerse en el idioma aceptado por el explorador.

## <a name="see-also"></a>Vea también

- [Globalización y localización](index.md)
- [Recursos de aplicaciones de escritorio](../../framework/resources/index.md)
