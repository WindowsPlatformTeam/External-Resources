# Ordering Rules

## The Abstract

Rules which enforce a standard ordering scheme for code contents.

## Rules

Within a class, struct or interface

* Constant Fields
* Fields
* Constructors
* Finalizers (Destructors)
* Delegates
* Enums
* Interfaces
* Properties
* Events
* Indexers
* Methods
* Structs
* Classes

Within each of these groups order by access

* public
* internal
* protected internal
* protected
* private

Within each of the access groups, order by static, then non-static

* static
* non-static

Within each of the static/non-static groups of fields, order by readonly, then non-readonly

* readonly
* non-readonly

An unrolled list is 130 lines long, so I won't unroll it here. The methods part unrolled is:

* public static methods
* public methods
* internal static methods
* internal methods
* protected internal static methods
* protected internal methods
* protected static methods
* protected methods
* private static methods
* private methods

The documentation notes that if the prescribed order isn't suitable - say, multiple interfaces are being implemented, and the interface methods and properties should be grouped together - then use a partial class to group the related methods and properties together.

## .Net Class Example - FrameworkElement

```csharp
namespace System.Windows
{
    public class FrameworkElement : Windows.UIElement, IFrameworkInputElement, Windows.IInputElement, ISupportInitialize, IHaveResources, Markup.IQueryAmbient
    {
        // Fields
        public static readonly Windows.DependencyProperty StyleProperty;
        public static readonly Windows.DependencyProperty MaxHeightProperty;
        public static readonly Windows.DependencyProperty FlowDirectionProperty;
        
        protected internal static readonly Windows.DependencyProperty DefaultStyleKeyProperty;
        
        // Constructor
        public FrameworkElement();
        
        // Properties
        public Media.Transform LayoutTransform { get; set; }
        public double Width { get; set; }
        public double MinWidth { get; set; }
        
        protected override int VisualChildrenCount { get; }
        protected internal InheritanceBehavior InheritanceBehavior { get; set; }
        protected internal virtual IEnumerator LogicalChildren { get; }
        protected internal object DefaultStyleKey { get; set; }
        
        // Events
        public event ToolTipEventHandler ToolTipClosing;
        public event ToolTipEventHandler ToolTipOpening;
        public event Windows.RoutedEventHandler Unloaded;
        public event Windows.DependencyPropertyChangedEventHandler DataContextChanged;
        public event SizeChangedEventHandler SizeChanged;
        
        // Methods
        public static Windows.FlowDirection GetFlowDirection(Windows.DependencyObject element);

        public bool ApplyTemplate();
        public virtual void BeginInit();
        public void BeginStoryboard(Storyboard storyboard);
        public virtual void EndInit();
        public object FindName(string name);
        public sealed override bool MoveFocus(Input.TraversalRequest request);
        public bool ShouldSerializeResources();
        
        protected sealed override void ArrangeCore(Windows.Rect finalRect);
        protected virtual Windows.Size ArrangeOverride(Windows.Size finalSize);
        protected override Media.Geometry GetLayoutClip(Windows.Size layoutSlotSize);
        protected override Media.Visual GetVisualChild(int index);
        protected sealed override Windows.Size MeasureCore(Windows.Size availableSize);
        protected virtual Windows.Size MeasureOverride(Windows.Size availableSize);
        protected virtual void OnContextMenuClosing(ContextMenuEventArgs e);
        protected virtual void OnContextMenuOpening(ContextMenuEventArgs e);
        protected override void OnGotFocus(Windows.RoutedEventArgs e);
        protected virtual void OnInitialized(EventArgs e);
        protected override void OnPropertyChanged(Windows.DependencyPropertyChangedEventArgs e);
        protected virtual void OnToolTipClosing(ToolTipEventArgs e);
        protected virtual void OnToolTipOpening(ToolTipEventArgs e);
        protected internal void AddLogicalChild(object child);
        protected internal Windows.DependencyObject GetTemplateChild(string childName);
        protected internal override Windows.DependencyObject GetUIParentCore();
        protected internal override void OnRenderSizeChanged(Windows.SizeChangedInfo sizeInfo);
        protected internal virtual void OnStyleChanged(Style oldStyle, Style newStyle);
        protected internal virtual void ParentLayoutInvalidated(Windows.UIElement child);
        protected internal void RemoveLogicalChild(object child);
    }
}
```

## References

* [StackOverflow](https://stackoverflow.com/questions/150479/order-of-items-in-classes-fields-properties-constructors-methods)
* StyleCop - StyleCop Rules [Documentation](http://stylecop.soyuz5.com/Ordering%20Rules.html)

