### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>Algunas API WorkFlow de arrastrar y colocar están obsoletas

|   |   |
|---|---|
|Detalles|Esta API WorkFlow de arrastrar y colocar está obsoleta y generará advertencias del compilador si la aplicación se vuelve a compilar en 4.5.|
|Sugerencia|En su lugar, se deben usar las API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> nuevas compatibles con operaciones con varios objetos. También es posible suprimir las advertencias de compilación o usar un compilador anterior para evitarlas. Las API siguen siendo compatibles.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|

