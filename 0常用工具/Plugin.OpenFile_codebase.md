# 项目代码汇总: Plugin.OpenFile

> 本文档由 DevPilotAI.Toolbox 自动生成，用于 AI 辅助开发、知识库上传或长上下文代码分析。
> 已自动过滤编译产物、缓存目录、IDE 临时文件和部分自动生成文件。
> 若需要修改代码，请优先依据每个代码块上方的“相对路径”定位原始项目文件。

## 1. 项目概览

- 项目名称: `Plugin.OpenFile`
- 项目路径: `D:\CSharpCode\PluginProject\PluginProject\02Plugins\000常用工具\Plugin.OpenFile`
- 生成时间: `2026-10-19 22:51:12`
- 导出文件数: `34`
- 输出策略: `全部允许类型文件`
- 单文件大小限制: `2 MB`
- 包含 Markdown 文档: `False`
- 包含 HTML 文档: `False`
- 导出后自动拆分: `False`
- 拆分容量限制: `2 MB`

### 1.1 导出选项

- 包含项目目录树: `True`
- 包含文件正文: `True`
- 包含文件元信息: `True`
- 跳过空文件: `True`

### 1.2 文件类型统计

- `.config`: `2` 个
- `.cs`: `29` 个
- `.csproj`: `1` 个
- `.xaml`: `2` 个

## 2. 项目结构树

```text
Plugin.OpenFile/
├── Converters/
│   └── Converters.cs
├── Model/
│   ├── DocumentItemModel.cs
│   ├── ExportSettings.cs
│   ├── FileContracts.cs
│   ├── FileEnums.cs
│   ├── FilePreviewModel.cs
│   ├── ImageCategoryModel.cs
│   ├── ImageItemModel.cs
│   └── OpenFileSettings.cs
├── Parsers/
│   ├── CsvParser.cs
│   ├── HalconSourceParser.cs
│   ├── IFileParser.cs
│   ├── JsonParser.cs
│   ├── MarkdownParser.cs
│   └── TextFileParser.cs
├── Platform/
│   ├── VmImagePlatformAdapter.cs
│   └── VmOutputPublisher.cs
├── Properties/
│   ├── AssemblyInfo.cs
│   └── DesignTimeResources.xaml
├── Services/
│   ├── DocumentPreviewService.cs
│   ├── EncodingDetectionService.cs
│   ├── FileRecognitionService.cs
│   ├── ImageImportService.cs
│   └── SampleExportService.cs
├── ViewModels/
│   ├── DocumentItemViewModel.cs
│   ├── ImageItemViewModel.cs
│   ├── OpenFileUiState.cs
│   ├── OpenFileViewModel.cs
│   └── RelayCommand.cs
├── Views/
│   ├── OpenFileView.xaml
│   └── OpenFileView.xaml.cs
├── app.config
├── packages.config
└── Plugin.OpenFile.csproj
```

## 3. 核心代码文件详情

### 文件 1: `Plugin.OpenFile.csproj`

- **相对路径**: `Plugin.OpenFile.csproj`
- **文件类型**: `C# 项目文件`
- **文件大小**: `5.52 KB`
- **概要**: C# 项目配置文件，包含目标框架、依赖包和构建配置

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProjectGuid>{7E4A2C91-8D63-4F52-B0A8-9C31D6E5F7A2}</ProjectGuid>
    <OutputType>library</OutputType>
    <RootNamespace>Plugin.OpenFile</RootNamespace>
    <AssemblyName>Plugin.OpenFile</AssemblyName>
    <TargetFrameworkVersion>v4.7.2</TargetFrameworkVersion>
    <FileAlignment>512</FileAlignment>
    <ProjectTypeGuids>{60dc8134-eba5-43b8-bcc9-bb4bc16c2548};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>
    <WarningLevel>4</WarningLevel>
    <Deterministic>true</Deterministic>
    <LangVersion>7.3</LangVersion>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>..\..\..\00Exe\Plugins\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>..\..\..\00Exe\Plugins\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="ControlzEx">
      <HintPath>..\..\..\00Exe\ControlzEx.dll</HintPath>
    </Reference>
    <Reference Include="EventMgrLib">
      <HintPath>..\..\..\00Exe\EventMgrLib.dll</HintPath>
    </Reference>
    <Reference Include="halcondotnet">
      <HintPath>..\..\..\00Exe\halcondotnet.dll</HintPath>
    </Reference>
    <Reference Include="HandyControl">
      <HintPath>..\..\..\00Exe\HandyControl.dll</HintPath>
    </Reference>
    <Reference Include="MahApps.Metro">
      <HintPath>..\..\..\00Exe\MahApps.Metro.dll</HintPath>
    </Reference>
    <Reference Include="Microsoft.Xaml.Behaviors">
      <HintPath>..\..\..\00Exe\Microsoft.Xaml.Behaviors.dll</HintPath>
    </Reference>
    <Reference Include="System" />
    <Reference Include="System.Data" />
    <Reference Include="System.Windows.Forms" />
    <Reference Include="System.Web.Extensions" />
    <Reference Include="System.Core" />
    <Reference Include="System.Xaml" />
    <Reference Include="System.Xml" />
    <Reference Include="Microsoft.CSharp" />
    <Reference Include="VM.Halcon">
      <HintPath>..\..\..\00Exe\VM.Halcon.dll</HintPath>
    </Reference>
    <Reference Include="VM.Start, Version=2.0.0.89, Culture=neutral, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\00Exe\VM.Start.exe</HintPath>
    </Reference>
    <Reference Include="WindowsBase" />
    <Reference Include="PresentationCore" />
    <Reference Include="PresentationFramework" />
    <Reference Include="WindowsFormsIntegration" />
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Model\FileContracts.cs" />
    <Compile Include="Model\FileEnums.cs" />
    <Compile Include="Model\ImageCategoryModel.cs" />
    <Compile Include="Model\ImageItemModel.cs" />
    <Compile Include="Model\DocumentItemModel.cs" />
    <Compile Include="Model\ExportSettings.cs" />
    <Compile Include="Model\FilePreviewModel.cs" />
    <Compile Include="Model\OpenFileSettings.cs" />
    <Compile Include="Services\EncodingDetectionService.cs" />
    <Compile Include="Services\FileRecognitionService.cs" />
    <Compile Include="Services\ImageImportService.cs" />
    <Compile Include="Services\DocumentPreviewService.cs" />
    <Compile Include="Services\SampleExportService.cs" />
    <Compile Include="Parsers\IFileParser.cs" />
    <Compile Include="Parsers\TextFileParser.cs" />
    <Compile Include="Parsers\MarkdownParser.cs" />
    <Compile Include="Parsers\CsvParser.cs" />
    <Compile Include="Parsers\JsonParser.cs" />
    <Compile Include="Parsers\HalconSourceParser.cs" />
    <Compile Include="Platform\VmImagePlatformAdapter.cs" />
    <Compile Include="Platform\VmOutputPublisher.cs" />
    <Compile Include="ViewModels\RelayCommand.cs" />
    <Compile Include="ViewModels\ImageItemViewModel.cs" />
    <Compile Include="ViewModels\DocumentItemViewModel.cs" />
    <Compile Include="ViewModels\OpenFileUiState.cs" />
    <Compile Include="ViewModels\OpenFileViewModel.cs" />
    <Compile Include="Views\OpenFileView.xaml.cs">
      <DependentUpon>OpenFileView.xaml</DependentUpon>
    </Compile>
    <Compile Include="Converters\Converters.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
  </ItemGroup>
  <ItemGroup>
    <Page Include="Properties\DesignTimeResources.xaml">
      <SubType>Designer</SubType>
      <Generator>MSBuild:Compile</Generator>
    </Page>
    <Page Include="Views\OpenFileView.xaml">
      <SubType>Designer</SubType>
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
  <ItemGroup>
    <None Include="app.config" />
    <None Include="packages.config" />
    <None Include="README.md" />
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

---

### 文件 2: `Views/OpenFileView.xaml`

- **相对路径**: `Views/OpenFileView.xaml`
- **文件类型**: `WPF/XAML 文件`
- **文件大小**: `57.96 KB`
- **概要**: WPF/XAML 界面布局或资源定义文件

```xml
<vb:ModuleViewBase x:Class="Plugin.OpenFile.Views.OpenFileView"
                   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                   xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
                   xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
                   xmlns:vb="clr-namespace:VM.Start.Core;assembly=VM.Start"
                   xmlns:mah="http://metro.mahapps.com/winfx/xaml/controls"
                   xmlns:WinFormHost="clr-namespace:System.Windows.Forms.Integration;assembly=WindowsFormsIntegration"
                   xmlns:hw="clr-namespace:VM.Halcon;assembly=VM.Halcon"
                   xmlns:cvt="clr-namespace:Plugin.OpenFile.Converters"
                   mc:Ignorable="d"
                   Height="720" Width="1100"
                   MinWidth="980" MinHeight="620"
                   FontFamily="Segoe UI, Microsoft YaHei UI"
                   Background="{DynamicResource WindowBackground}"
                   Foreground="{DynamicResource TextPrimary}">
    <vb:ModuleViewBase.Resources>
        <ResourceDictionary>
            <!-- 仅本地转换器与隐式样式；禁止合并 Collection.xaml/ThemeTokens/MahApps 固定主题（主题合规 F1/F8） -->
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary />
            </ResourceDictionary.MergedDictionaries>

            <cvt:FileTypeToIconConverter x:Key="FileTypeToIcon" />
            <cvt:StatusToBrushConverter x:Key="StatusToBrush" />
            <cvt:PreviewModeToVisibilityConverter x:Key="PreviewModeToVisibility" />
            <cvt:EnumTextConverter x:Key="EnumText" />

            <!-- 本地隐式语义样式：控件随宿主 Light/Dark 切换（§7 范式块） -->
            <Style TargetType="{x:Type GroupBox}" BasedOn="{StaticResource MahApps.Styles.GroupBox}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="BorderThickness" Value="1" />
                <Setter Property="Padding" Value="8,6" />
                <Setter Property="Margin" Value="0,0,0,8" />
                <Setter Property="mah:HeaderedControlHelper.HeaderBackground" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="mah:HeaderedControlHelper.HeaderForeground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="mah:HeaderedControlHelper.HeaderFontSize" Value="12.5" />
                <Setter Property="mah:HeaderedControlHelper.HeaderFontWeight" Value="SemiBold" />
            </Style>
            <Style TargetType="{x:Type TextBox}" BasedOn="{StaticResource MahApps.Styles.TextBox}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="Padding" Value="6,2" />
                <Setter Property="MinHeight" Value="28" />
                <Setter Property="Height" Value="28" />
                <Setter Property="VerticalContentAlignment" Value="Center" />
                <Setter Property="CaretBrush" Value="{DynamicResource TextPrimary}" />
                <Setter Property="SelectionBrush" Value="{DynamicResource Accent}" />
            </Style>
            <Style TargetType="{x:Type ComboBox}" BasedOn="{StaticResource MahApps.Styles.ComboBox}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="Height" Value="28" />
                <Setter Property="Padding" Value="6,2" />
                <Setter Property="VerticalContentAlignment" Value="Center" />
            </Style>
            <Style TargetType="{x:Type CheckBox}" BasedOn="{StaticResource MahApps.Styles.CheckBox}">
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="Margin" Value="0,2" />
            </Style>
            <Style TargetType="{x:Type Button}" BasedOn="{StaticResource VmButton}">
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="MinHeight" Value="28" />
                <Setter Property="Height" Value="28" />
                <Setter Property="Padding" Value="10,3" />
                <Setter Property="Cursor" Value="Hand" />
            </Style>
            <Style x:Key="OpenFilePlugin.PrimaryButtonStyle"
                   TargetType="{x:Type Button}"
                   BasedOn="{StaticResource VmButton}">
                <Setter Property="Background" Value="{DynamicResource Accent}" />
                <Setter Property="Foreground" Value="{DynamicResource ContentTextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource Accent}" />
                <Setter Property="MinHeight" Value="28" />
                <Setter Property="Height" Value="28" />
                <Setter Property="Padding" Value="12,3" />
                <Setter Property="FontWeight" Value="SemiBold" />
                <Setter Property="Cursor" Value="Hand" />
            </Style>
            <Style TargetType="{x:Type ListBox}" BasedOn="{StaticResource MahApps.Styles.ListBox}">
                <Setter Property="Background" Value="Transparent" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="BorderThickness" Value="1" />
                <Setter Property="Padding" Value="4" />
            </Style>
            <Style TargetType="{x:Type TabControl}" BasedOn="{StaticResource MahApps.Styles.TabControl}">
                <Setter Property="Background" Value="{DynamicResource WindowBackground}" />
                <Setter Property="Padding" Value="0" />
                <Setter Property="mah:TabControlHelper.Underlined" Value="TabItems" />
                <Setter Property="mah:TabControlHelper.UnderlineSelectedBrush" Value="{DynamicResource Accent}" />
                <Setter Property="mah:TabControlHelper.UnderlineBrush" Value="Transparent" />
            </Style>
            <Style TargetType="{x:Type TabItem}" BasedOn="{StaticResource MahApps.Styles.TabItem}">
                <Setter Property="Foreground" Value="{DynamicResource TextSecondary}" />
                <Setter Property="Padding" Value="16,6" />
                <Setter Property="mah:HeaderedControlHelper.HeaderFontSize" Value="14" />
                <Setter Property="mah:HeaderedControlHelper.HeaderFontWeight" Value="SemiBold" />
                <Setter Property="Cursor" Value="Hand" />
                <Style.Triggers>
                    <Trigger Property="IsSelected" Value="True">
                        <Setter Property="Foreground" Value="{DynamicResource Accent}" />
                    </Trigger>
                </Style.Triggers>
            </Style>
            <Style x:Key="OpenFilePlugin.DataGridColumnHeaderStyle"
                   TargetType="{x:Type DataGridColumnHeader}"
                   BasedOn="{StaticResource MahApps.Styles.DataGridColumnHeader}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="BorderThickness" Value="0,0,0,1" />
                <Setter Property="Padding" Value="8,4" />
                <Setter Property="FontWeight" Value="SemiBold" />
            </Style>
            <Style x:Key="OpenFilePlugin.DataGridRowStyle"
                   TargetType="{x:Type DataGridRow}"
                   BasedOn="{StaticResource MahApps.Styles.DataGridRow}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackground}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Style.Triggers>
                    <Trigger Property="IsSelected" Value="True">
                        <Setter Property="Background" Value="{DynamicResource Accent}" />
                        <Setter Property="Foreground" Value="{DynamicResource ContentTextPrimary}" />
                    </Trigger>
                </Style.Triggers>
            </Style>
            <Style x:Key="OpenFilePlugin.DataGridCellStyle"
                   TargetType="{x:Type DataGridCell}"
                   BasedOn="{StaticResource MahApps.Styles.DataGridCell}">
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
            </Style>
            <Style TargetType="{x:Type DataGrid}" BasedOn="{StaticResource MahApps.Styles.DataGrid}">
                <Setter Property="Background" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                <Setter Property="BorderBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="BorderThickness" Value="1" />
                <Setter Property="RowBackground" Value="{DynamicResource SurfaceBackground}" />
                <Setter Property="AlternatingRowBackground" Value="{DynamicResource SurfaceBackgroundSecondary}" />
                <Setter Property="HorizontalGridLinesBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="VerticalGridLinesBrush" Value="{DynamicResource BorderSubtle}" />
                <Setter Property="ColumnHeaderStyle" Value="{StaticResource OpenFilePlugin.DataGridColumnHeaderStyle}" />
                <Setter Property="RowStyle" Value="{StaticResource OpenFilePlugin.DataGridRowStyle}" />
                <Setter Property="CellStyle" Value="{StaticResource OpenFilePlugin.DataGridCellStyle}" />
            </Style>
        </ResourceDictionary>
    </vb:ModuleViewBase.Resources>

    <!-- 根内容 Grid：窗口级语义背景 + 文本色（§3 结构语义化） -->
    <Grid Background="{DynamicResource WindowBackground}" TextElement.Foreground="{DynamicResource TextPrimary}"
          AllowDrop="True" Drop="View_Drop">
        <Grid.RowDefinitions>
            <RowDefinition Height="*" />
            <RowDefinition Height="Auto" />
        </Grid.RowDefinitions>

        <TabControl Grid.Row="0" Margin="10,10,10,0">

            <!-- ============ Tab 1：图像导入与标注 ============ -->
            <TabItem Header="图像导入与标注">
                <Grid Background="{DynamicResource SurfaceBackground}" Margin="6">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="*" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>

                    <!-- 工具栏卡片容器 -->
                    <Border Grid.Row="0" Margin="0,0,0,8"
                            Background="{DynamicResource SurfaceBackgroundSecondary}"
                            BorderBrush="{DynamicResource BorderSubtle}"
                            BorderThickness="1"
                            CornerRadius="4"
                            Padding="8,5">
                        <WrapPanel VerticalAlignment="Center">
                            <!-- 组1：文件操作 -->
                            <Button Content="添加图像" Command="{Binding AddImagesCommand}"
                                    Style="{StaticResource OpenFilePlugin.PrimaryButtonStyle}"
                                    MinWidth="72" Margin="0,0,6,0" />
                            <Button Content="添加文件夹" Command="{Binding AddImageFolderCommand}"
                                    MinWidth="76" Margin="0,0,6,0" />
                            <Button Content="移除选中" Command="{Binding RemoveImageCommand}"
                                    MinWidth="64" Margin="0,0,6,0" />
                            <Button Content="清空清单" Command="{Binding ClearImagesCommand}"
                                    MinWidth="64" Margin="0,0,6,0" />

                            <!-- 分隔线 -->
                            <Rectangle Width="1" Height="18" Fill="{DynamicResource BorderSubtle}" Margin="6,0" VerticalAlignment="Center" />

                            <!-- 组2：筛选 -->
                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                                <TextBlock Text="筛选:" VerticalAlignment="Center" Foreground="{DynamicResource TextSecondary}" Margin="0,0,6,0" />
                                <ComboBox x:Name="FilterCombo" Width="105" Height="28" Margin="0,0,6,0"
                                          ItemsSource="{Binding Ui.Categories}"
                                          DisplayMemberPath="Name" SelectedValuePath="Id"
                                          SelectionChanged="FilterCombo_SelectionChanged" />
                            </StackPanel>

                            <!-- 分隔线 -->
                            <Rectangle Width="1" Height="18" Fill="{DynamicResource BorderSubtle}" Margin="6,0" VerticalAlignment="Center" />

                            <!-- 组3：模板 -->
                            <Button Content="设为模板" Command="{Binding SetTemplateCommand}"
                                    MinWidth="68" Margin="0,0,6,0" />
                            <Button Content="取消模板" Command="{Binding ClearTemplateCommand}"
                                    MinWidth="68" Margin="0,0,6,0" />

                            <!-- 分隔线 -->
                            <Rectangle Width="1" Height="18" Fill="{DynamicResource BorderSubtle}" Margin="6,0" VerticalAlignment="Center" />

                            <!-- 组4：标注分类 -->
                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                                <TextBlock Text="标注为:" VerticalAlignment="Center" Foreground="{DynamicResource TextSecondary}" Margin="0,0,6,0" />
                                <ComboBox Width="95" Height="28" Margin="0,0,6,0"
                                          ItemsSource="{Binding Ui.Categories}"
                                          DisplayMemberPath="Name"
                                          SelectedItem="{Binding Ui.AssignCategory, Mode=TwoWay}" />
                                <Button Content="标注选中" Command="{Binding AssignCategoryCommand}"
                                        MinWidth="68" Margin="0,0,6,0" />
                                <Button Content="批量标注" Command="{Binding BatchAssignCategoryCommand}"
                                        CommandParameter="{Binding SelectedItems, ElementName=ImageList}"
                                        MinWidth="68" Margin="0,0,0,0" />
                            </StackPanel>
                        </WrapPanel>
                    </Border>

                    <!-- 主区：列表 | 显示 | 信息 -->
                    <Grid Grid.Row="1">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="230" />
                            <ColumnDefinition Width="*" />
                            <ColumnDefinition Width="310" />
                        </Grid.ColumnDefinitions>

                        <!-- 左侧图像缩略图列表 -->
                        <Border Grid.Column="0" Margin="0,0,8,0"
                                BorderBrush="{DynamicResource BorderSubtle}"
                                BorderThickness="1"
                                CornerRadius="4"
                                Background="{DynamicResource SurfaceBackgroundSecondary}"
                                ClipToBounds="True">
                            <Grid>
                                <!-- 空数据引导提示（不遮挡点击） -->
                                <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center"
                                            IsHitTestVisible="False" Opacity="0.45" Margin="12">
                                    <TextBlock Text="🖼" FontSize="26" HorizontalAlignment="Center" Margin="0,0,0,6" />
                                    <TextBlock Text="暂无图像" FontSize="12" FontWeight="SemiBold" HorizontalAlignment="Center" Margin="0,0,0,2"
                                               Foreground="{DynamicResource TextPrimary}" />
                                    <TextBlock Text="拖拽图像或文件夹至此" FontSize="11" TextAlignment="Center"
                                               Foreground="{DynamicResource TextSecondary}" TextWrapping="Wrap" />
                                </StackPanel>

                                <ListBox x:Name="ImageList"
                                         ItemsSource="{Binding Ui.FilteredImages}"
                                         SelectedItem="{Binding Ui.SelectedImage, Mode=OneWay}"
                                         ScrollViewer.HorizontalScrollBarVisibility="Disabled"
                                         SelectionMode="Extended"
                                         Background="Transparent"
                                         BorderThickness="0"
                                         Padding="4"
                                         SelectionChanged="ImageList_SelectionChanged">
                                    <ListBox.ItemsPanel>
                                        <ItemsPanelTemplate>
                                            <WrapPanel />
                                        </ItemsPanelTemplate>
                                    </ListBox.ItemsPanel>
                                    <ListBox.ItemTemplate>
                                        <DataTemplate>
                                            <Border Width="98" Margin="3" Padding="4"
                                                    Background="{DynamicResource SurfaceBackground}"
                                                    BorderBrush="{DynamicResource BorderSubtle}"
                                                    BorderThickness="1"
                                                    CornerRadius="3">
                                                <StackPanel>
                                                    <Border Height="72" Background="#FF101216" CornerRadius="2" ClipToBounds="True">
                                                        <Image Stretch="Uniform"
                                                               Source="{Binding Thumbnail, Mode=OneWay}" />
                                                    </Border>
                                                    <TextBlock Text="{Binding DisplayName, Mode=OneWay}" FontSize="11"
                                                               FontWeight="Medium" Margin="0,3,0,1"
                                                               TextTrimming="CharacterEllipsis"
                                                               Foreground="{DynamicResource TextPrimary}" />
                                                    <TextBlock Text="{Binding OrderText, Mode=OneWay}" FontSize="10"
                                                               Foreground="{DynamicResource TextSecondary}" />
                                                </StackPanel>
                                            </Border>
                                        </DataTemplate>
                                    </ListBox.ItemTemplate>
                                </ListBox>
                            </Grid>
                        </Border>

                        <!-- 中间编辑器预览窗口（带外框，与工作流输出隔离） -->
                        <Border Grid.Column="1" Margin="0,0,8,0"
                                BorderBrush="{DynamicResource BorderSubtle}"
                                BorderThickness="1"
                                CornerRadius="4"
                                Background="#FF0B0E14"
                                ClipToBounds="True">
                            <WinFormHost:WindowsFormsHost>
                                <hw:VMHWindowControl x:Name="PreviewWindow" />
                            </WinFormHost:WindowsFormsHost>
                        </Border>

                        <!-- 右侧侧边栏：样本信息 + 样本导出 -->
                        <ScrollViewer Grid.Column="2" VerticalScrollBarVisibility="Auto" HorizontalScrollBarVisibility="Disabled">
                            <StackPanel>
                                <!-- 样本信息卡片 -->
                                <GroupBox Header="样本信息" Margin="0,0,0,8">
                                    <StackPanel Margin="2">
                                        <TextBlock Text="{Binding Ui.SelectedImage.DisplayName, Mode=OneWay}"
                                                   FontWeight="Bold" FontSize="13" TextTrimming="CharacterEllipsis" />
                                        <TextBlock Text="{Binding Ui.SelectedImage.SourcePath, Mode=OneWay}"
                                                   FontSize="11" TextTrimming="CharacterEllipsis"
                                                   ToolTip="{Binding Ui.SelectedImage.SourcePath, Mode=OneWay}"
                                                   Foreground="{DynamicResource TextSecondary}" Margin="0,2,0,6" />
                                        <Grid Margin="0,2,0,6">
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="42" />
                                                <ColumnDefinition Width="*" />
                                            </Grid.ColumnDefinitions>
                                            <Grid.RowDefinitions>
                                                <RowDefinition Height="Auto" />
                                                <RowDefinition Height="Auto" />
                                                <RowDefinition Height="Auto" />
                                                <RowDefinition Height="Auto" />
                                            </Grid.RowDefinitions>
                                            <TextBlock Grid.Row="0" Grid.Column="0" Text="规格:" Foreground="{DynamicResource TextSecondary}" Margin="0,2" />
                                            <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Ui.SelectedImage.MetaText, Mode=OneWay}" Margin="0,2" />

                                            <TextBlock Grid.Row="1" Grid.Column="0" Text="大小:" Foreground="{DynamicResource TextSecondary}" Margin="0,2" />
                                            <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Ui.SelectedImage.SizeText, Mode=OneWay}" Margin="0,2" />

                                            <TextBlock Grid.Row="2" Grid.Column="0" Text="状态:" Foreground="{DynamicResource TextSecondary}" Margin="0,2" />
                                            <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Ui.SelectedImage.StatusText, Mode=OneWay}" Margin="0,2"
                                                       Foreground="{Binding Ui.SelectedImage.StatusText, Converter={StaticResource StatusToBrush}, Mode=OneWay}"
                                                       FontWeight="SemiBold" />

                                            <TextBlock Grid.Row="3" Grid.Column="0" Text="模板:" Foreground="{DynamicResource TextSecondary}" Margin="0,2" />
                                            <TextBlock Grid.Row="3" Grid.Column="1" Margin="0,2"
                                                       Text="{Binding Ui.SelectedTemplateMarker, Mode=OneWay, Converter={StaticResource EnumText}, ConverterParameter=template}" />
                                        </Grid>

                                        <Rectangle Height="1" Fill="{DynamicResource BorderSubtle}" Margin="0,2,0,6" />

                                        <TextBlock Text="备注:" FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,0,3" />
                                        <TextBox Text="{Binding Ui.RemarkText, UpdateSourceTrigger=LostFocus}"
                                                 mah:TextBoxHelper.Watermark="输入样本备注…"
                                                 Height="28" MinHeight="28"
                                                 LostFocus="RemarkBox_LostFocus" />
                                    </StackPanel>
                                </GroupBox>

                                <!-- 样本导出卡片 -->
                                <GroupBox Header="样本导出" Margin="0,0,0,0">
                                    <StackPanel Margin="2">
                                        <TextBlock Text="目标目录:" FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,0,3" />
                                        <Grid Margin="0,0,0,6">
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="*" />
                                                <ColumnDefinition Width="Auto" />
                                            </Grid.ColumnDefinitions>
                                            <TextBox Grid.Column="0" Text="{Binding Ui.ExportTargetDirectory, Mode=TwoWay, UpdateSourceTrigger=LostFocus}"
                                                     mah:TextBoxHelper.Watermark="请选择导出目标目录…" Height="28" />
                                            <Button Grid.Column="1" Content="浏览…" Margin="6,0,0,0" MinWidth="54" Height="28"
                                                    Click="BrowseExport_Click" />
                                        </Grid>

                                        <Grid Margin="0,0,0,6">
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="1.1*" />
                                                <ColumnDefinition Width="*" />
                                            </Grid.ColumnDefinitions>
                                            <StackPanel Grid.Column="0" Margin="0,0,6,0">
                                                <TextBlock Text="范围:" FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,0,2" />
                                                <ComboBox SelectedItem="{Binding Ui.ExportScope, Mode=TwoWay}"
                                                          ItemsSource="{Binding Ui.ExportScopes}" Height="26" Margin="0,0,0,4">
                                                    <ComboBox.ItemTemplate>
                                                        <DataTemplate>
                                                            <TextBlock Text="{Binding Converter={StaticResource EnumText}}" />
                                                        </DataTemplate>
                                                    </ComboBox.ItemTemplate>
                                                </ComboBox>

                                                <TextBlock Text="目录:" FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,0,2" />
                                                <ComboBox SelectedItem="{Binding Ui.ExportFolderMode, Mode=TwoWay}"
                                                          ItemsSource="{Binding Ui.FolderModes}" Height="26" Margin="0,0,0,4">
                                                    <ComboBox.ItemTemplate>
                                                        <DataTemplate>
                                                            <TextBlock Text="{Binding Converter={StaticResource EnumText}}" />
                                                        </DataTemplate>
                                                    </ComboBox.ItemTemplate>
                                                </ComboBox>

                                                <TextBlock Text="冲突:" FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,0,2" />
                                                <ComboBox SelectedItem="{Binding Ui.ExportConflict, Mode=TwoWay}"
                                                          ItemsSource="{Binding Ui.ConflictPolicies}" Height="26">
                                                    <ComboBox.ItemTemplate>
                                                        <DataTemplate>
                                                            <TextBlock Text="{Binding Converter={StaticResource EnumText}}" />
                                                        </DataTemplate>
                                                    </ComboBox.ItemTemplate>
                                                </ComboBox>
                                            </StackPanel>

                                            <StackPanel Grid.Column="1" Margin="4,4,0,0" VerticalAlignment="Center">
                                                <CheckBox Content="含未标注" IsChecked="{Binding Ui.ExportIncludeUnlabeled, Mode=TwoWay}" Margin="0,3" />
                                                <CheckBox Content="含模板副本" IsChecked="{Binding Ui.ExportIncludeTemplateCopy, Mode=TwoWay}" Margin="0,3" />
                                                <CheckBox Content="生成清单" IsChecked="{Binding Ui.ExportWriteManifest, Mode=TwoWay}" Margin="0,3" />
                                                <CheckBox Content="保留相对路径" IsChecked="{Binding Ui.ExportPreserveRelativePath, Mode=TwoWay}" Margin="0,3" />
                                            </StackPanel>
                                        </Grid>

                                        <!-- 导出操作按钮组（横排并列节省垂直空间） -->
                                        <Grid Margin="0,4,0,4">
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="*" />
                                                <ColumnDefinition Width="*" />
                                            </Grid.ColumnDefinitions>
                                            <Button Grid.Column="0" Content="导出样本" Command="{Binding ExportSamplesCommand}"
                                                    Height="30" Margin="0,0,4,0"
                                                    Style="{StaticResource OpenFilePlugin.PrimaryButtonStyle}" />
                                            <Button Grid.Column="1" Content="取消导出" Command="{Binding CancelExportCommand}"
                                                    Height="30" Margin="4,0,0,0" />
                                        </Grid>

                                        <TextBlock Text="{Binding Ui.ExportProgressText, Mode=OneWay}" FontSize="11"
                                                   TextTrimming="CharacterEllipsis" ToolTip="{Binding Ui.ExportProgressText, Mode=OneWay}"
                                                   Foreground="{DynamicResource TextSecondary}" Margin="0,2,0,0" />
                                    </StackPanel>
                                </GroupBox>
                            </StackPanel>
                        </ScrollViewer>
                    </Grid>
                </Grid>
            </TabItem>

            <!-- ============ Tab 2：文档与数据预览 ============ -->
            <TabItem Header="文档与数据预览">
                <Grid Background="{DynamicResource SurfaceBackground}" Margin="6">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="*" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>

                    <!-- 工具栏卡片容器 -->
                    <Border Grid.Row="0" Margin="0,0,0,8"
                            Background="{DynamicResource SurfaceBackgroundSecondary}"
                            BorderBrush="{DynamicResource BorderSubtle}"
                            BorderThickness="1"
                            CornerRadius="4"
                            Padding="8,5">
                        <WrapPanel VerticalAlignment="Center">
                            <!-- 组1：文档操作 -->
                            <Button Content="打开文档" Command="{Binding OpenDocumentCommand}"
                                    Style="{StaticResource OpenFilePlugin.PrimaryButtonStyle}"
                                    MinWidth="76" Margin="0,0,6,0" />
                            <Button Content="移除选中" Command="{Binding RemoveDocumentCommand}"
                                    MinWidth="64" Margin="0,0,6,0" />
                            <Button Content="清空清单" Command="{Binding ClearDocumentsCommand}"
                                    MinWidth="64" Margin="0,0,6,0" />

                            <!-- 分隔线 -->
                            <Rectangle Width="1" Height="18" Fill="{DynamicResource BorderSubtle}" Margin="6,0" VerticalAlignment="Center" />

                            <!-- 组2：格式与编码 -->
                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                                <TextBlock Text="编码:" VerticalAlignment="Center" Foreground="{DynamicResource TextSecondary}" Margin="0,0,6,0" />
                                <ComboBox Width="85" Height="28" Margin="0,0,8,0"
                                          ItemsSource="{Binding Ui.EncodingOptions}"
                                          SelectedItem="{Binding Ui.SelectedEncodingName, Mode=TwoWay}" />

                                <TextBlock Text="模式:" VerticalAlignment="Center" Foreground="{DynamicResource TextSecondary}" Margin="0,0,6,0" />
                                <ComboBox Width="80" Height="28" Margin="0,0,8,0"
                                          ItemsSource="{Binding Ui.PreviewModes}"
                                          SelectedItem="{Binding Ui.PreviewMode, Mode=TwoWay}">
                                    <ComboBox.ItemTemplate>
                                        <DataTemplate>
                                            <TextBlock Text="{Binding Converter={StaticResource EnumText}}" />
                                        </DataTemplate>
                                    </ComboBox.ItemTemplate>
                                </ComboBox>

                                <Button Content="重新解析" Command="{Binding ReloadPreviewCommand}"
                                        MinWidth="68" Margin="0,0,6,0" />
                                <Button Content="CSV转MD" Command="{Binding ConvertCsvToMarkdownCommand}"
                                        MinWidth="68" Margin="0,0,6,0" />
                            </StackPanel>

                            <!-- 分隔线 -->
                            <Rectangle Width="1" Height="18" Fill="{DynamicResource BorderSubtle}" Margin="6,0" VerticalAlignment="Center" />

                            <!-- 组3：搜索 -->
                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                                <TextBox Width="150" Height="28" Margin="0,0,6,0"
                                         Text="{Binding Ui.SearchText, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"
                                         mah:TextBoxHelper.Watermark="搜索内容…" />
                                <Button Content="搜索" Command="{Binding SearchCommand}"
                                        Style="{StaticResource OpenFilePlugin.PrimaryButtonStyle}"
                                        MinWidth="56" Margin="0,0,8,0" />
                                <TextBlock Text="{Binding Ui.MatchCountText, Mode=OneWay}" VerticalAlignment="Center"
                                           Foreground="{DynamicResource TextSecondary}" />
                            </StackPanel>
                        </WrapPanel>
                    </Border>

                    <!-- 主区：文档列表 | 预览内容 -->
                    <Grid Grid.Row="1">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="230" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>

                        <!-- 左侧文档列表 -->
                        <Border Grid.Column="0" Margin="0,0,8,0"
                                BorderBrush="{DynamicResource BorderSubtle}"
                                BorderThickness="1"
                                CornerRadius="4"
                                Background="{DynamicResource SurfaceBackgroundSecondary}"
                                ClipToBounds="True">
                            <Grid>
                                <!-- 空状态提示 -->
                                <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center"
                                            IsHitTestVisible="False" Opacity="0.45" Margin="12">
                                    <TextBlock Text="📄" FontSize="26" HorizontalAlignment="Center" Margin="0,0,0,6" />
                                    <TextBlock Text="暂无文档" FontSize="12" FontWeight="SemiBold" HorizontalAlignment="Center" Margin="0,0,0,2"
                                               Foreground="{DynamicResource TextPrimary}" />
                                    <TextBlock Text="拖拽文档文件至此" FontSize="11" TextAlignment="Center"
                                               Foreground="{DynamicResource TextSecondary}" TextWrapping="Wrap" />
                                </StackPanel>

                                <ListBox x:Name="DocumentList"
                                         ItemsSource="{Binding Ui.Documents}"
                                         SelectedItem="{Binding Ui.SelectedDocument, Mode=OneWay}"
                                         Background="Transparent"
                                         BorderThickness="0"
                                         Padding="4"
                                         SelectionChanged="DocumentList_SelectionChanged">
                                    <ListBox.ItemTemplate>
                                        <DataTemplate>
                                            <Border Margin="2" Padding="8,6"
                                                    Background="{DynamicResource SurfaceBackground}"
                                                    BorderBrush="{DynamicResource BorderSubtle}"
                                                    BorderThickness="1"
                                                    CornerRadius="3">
                                                <StackPanel>
                                                    <TextBlock Text="{Binding DisplayName, Mode=OneWay}" FontWeight="SemiBold"
                                                               TextTrimming="CharacterEllipsis"
                                                               Foreground="{DynamicResource TextPrimary}" />
                                                    <Grid Margin="0,4,0,0">
                                                        <Grid.ColumnDefinitions>
                                                            <ColumnDefinition Width="*" />
                                                            <ColumnDefinition Width="Auto" />
                                                        </Grid.ColumnDefinitions>
                                                        <StackPanel Grid.Column="0" Orientation="Horizontal">
                                                            <TextBlock Text="{Binding TypeText, Mode=OneWay}" FontSize="10"
                                                                       Foreground="{DynamicResource TextSecondary}" />
                                                            <TextBlock Text="{Binding SizeText, Mode=OneWay}" FontSize="10"
                                                                       Margin="6,0,0,0"
                                                                       Foreground="{DynamicResource TextSecondary}" />
                                                        </StackPanel>
                                                        <TextBlock Grid.Column="1" Text="{Binding StatusText, Mode=OneWay}" FontSize="10"
                                                                   FontWeight="SemiBold"
                                                                   Foreground="{Binding StatusText, Converter={StaticResource StatusToBrush}, Mode=OneWay}" />
                                                    </Grid>
                                                </StackPanel>
                                            </Border>
                                        </DataTemplate>
                                    </ListBox.ItemTemplate>
                                </ListBox>
                            </Grid>
                        </Border>

                        <!-- 右侧预览区容器 -->
                        <Border Grid.Column="1"
                                BorderBrush="{DynamicResource BorderSubtle}"
                                BorderThickness="1"
                                CornerRadius="4"
                                Background="{DynamicResource SurfaceBackgroundSecondary}"
                                ClipToBounds="True">
                            <Grid>
                                <TextBox Visibility="{Binding Ui.PreviewMode, Converter={StaticResource PreviewModeToVisibility}, ConverterParameter=Original}"
                                         Text="{Binding Ui.OriginalText, Mode=OneWay}"
                                         IsReadOnly="True" VerticalScrollBarVisibility="Auto"
                                         HorizontalScrollBarVisibility="Auto"
                                         BorderThickness="0"
                                         Background="Transparent"
                                         Padding="8"
                                         FontFamily="Consolas" TextWrapping="NoWrap" />
                                <DataGrid Visibility="{Binding Ui.PreviewMode, Converter={StaticResource PreviewModeToVisibility}, ConverterParameter=Table}"
                                          ItemsSource="{Binding Ui.PreviewTable, Mode=OneWay}"
                                          AutoGenerateColumns="True" IsReadOnly="True"
                                          BorderThickness="0"
                                          EnableRowVirtualization="True" EnableColumnVirtualization="True" />
                                <TextBox Visibility="{Binding Ui.PreviewMode, Converter={StaticResource PreviewModeToVisibility}, ConverterParameter=Formatted}"
                                         Text="{Binding Ui.FormattedText, Mode=OneWay}"
                                         IsReadOnly="True" VerticalScrollBarVisibility="Auto"
                                         HorizontalScrollBarVisibility="Auto"
                                         BorderThickness="0"
                                         Background="Transparent"
                                         Padding="8"
                                         FontFamily="Consolas" TextWrapping="NoWrap" />
                                <ScrollViewer Visibility="{Binding Ui.PreviewMode, Converter={StaticResource PreviewModeToVisibility}, ConverterParameter=Rendered}"
                                              VerticalScrollBarVisibility="Auto">
                                    <ItemsControl ItemsSource="{Binding Ui.RenderBlocks, Mode=OneWay}" Margin="10">
                                        <ItemsControl.ItemTemplate>
                                            <DataTemplate>
                                                <ContentControl>
                                                    <ContentControl.Style>
                                                        <Style TargetType="ContentControl">
                                                            <!-- 默认模板（段落/列表项）：必须置于 Style 内，否则局部值优先级压过触发器 -->
                                                            <Setter Property="Template">
                                                                <Setter.Value>
                                                                    <ControlTemplate TargetType="ContentControl">
                                                                        <StackPanel Orientation="Horizontal" Margin="0,3">
                                                                            <TextBlock Text="• " FontWeight="Bold">
                                                                                <TextBlock.Style>
                                                                                    <Style TargetType="TextBlock">
                                                                                        <Setter Property="Foreground" Value="{DynamicResource TextPrimary}" />
                                                                                        <Setter Property="Visibility" Value="Collapsed" />
                                                                                        <Style.Triggers>
                                                                                            <DataTrigger Binding="{Binding BlockType}" Value="ListItem">
                                                                                                <Setter Property="Visibility" Value="Visible" />
                                                                                            </DataTrigger>
                                                                                        </Style.Triggers>
                                                                                    </Style>
                                                                                </TextBlock.Style>
                                                                            </TextBlock>
                                                                            <TextBlock Text="{Binding Text}" TextWrapping="Wrap"
                                                                                       Foreground="{DynamicResource TextPrimary}" />
                                                                        </StackPanel>
                                                                    </ControlTemplate>
                                                                </Setter.Value>
                                                            </Setter>
                                                            <Style.Triggers>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="Heading1">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <TextBlock Text="{Binding Text}" FontSize="18" FontWeight="Bold"
                                                                                           Foreground="{DynamicResource TextPrimary}" Margin="0,8,0,4" />
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="Heading2">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <TextBlock Text="{Binding Text}" FontSize="15" FontWeight="Bold"
                                                                                           Foreground="{DynamicResource TextPrimary}" Margin="0,6,0,3" />
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="Heading3">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <TextBlock Text="{Binding Text}" FontSize="13" FontWeight="Bold"
                                                                                           Foreground="{DynamicResource TextPrimary}" Margin="0,4,0,2" />
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="CodeBlock">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <Border Background="#FF16181D" BorderBrush="{DynamicResource BorderSubtle}" BorderThickness="1" CornerRadius="3" Padding="8" Margin="0,4">
                                                                                    <TextBlock Text="{Binding Text}" FontFamily="Consolas" TextWrapping="Wrap"
                                                                                               Foreground="#FFD4D4D4" />
                                                                                </Border>
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="Quote">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <Border BorderThickness="3,0,0,0" BorderBrush="{DynamicResource Accent}" Background="{DynamicResource SurfaceBackground}" Padding="8,4" Margin="0,3">
                                                                                    <TextBlock Text="{Binding Text}" TextWrapping="Wrap"
                                                                                               Foreground="{DynamicResource TextSecondary}" />
                                                                                </Border>
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                                <DataTrigger Binding="{Binding BlockType}" Value="Separator">
                                                                    <Setter Property="Template">
                                                                        <Setter.Value>
                                                                            <ControlTemplate TargetType="ContentControl">
                                                                                <Separator Margin="0,6" />
                                                                            </ControlTemplate>
                                                                        </Setter.Value>
                                                                    </Setter>
                                                                </DataTrigger>
                                                            </Style.Triggers>
                                                        </Style>
                                                    </ContentControl.Style>
                                                </ContentControl>
                                            </DataTemplate>
                                        </ItemsControl.ItemTemplate>
                                    </ItemsControl>
                                </ScrollViewer>
                            </Grid>
                        </Border>
                    </Grid>

                    <TextBlock Grid.Row="2" Text="{Binding Ui.PreviewStatusText, Mode=OneWay}" FontSize="11"
                               TextWrapping="Wrap" Margin="0,6,0,0"
                               Foreground="{DynamicResource TextSecondary}" />
                </Grid>
            </TabItem>
        </TabControl>

        <!-- 底部状态栏：供图模式 + 执行 + 状态 -->
        <Border Grid.Row="1" Background="{DynamicResource SurfaceBackgroundSecondary}"
                BorderBrush="{DynamicResource BorderSubtle}" BorderThickness="1"
                CornerRadius="4" Margin="10,6,10,10" Padding="12,6">
            <Grid>
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="*" />
                </Grid.ColumnDefinitions>

                <!-- 供图设置 -->
                <StackPanel Grid.Column="0" Orientation="Horizontal" VerticalAlignment="Center">
                    <TextBlock Text="供图模式:" VerticalAlignment="Center" Foreground="{DynamicResource TextSecondary}" Margin="0,0,6,0" />
                    <ComboBox Width="110" Height="28" ItemsSource="{Binding Ui.SupplyModes}"
                              SelectedItem="{Binding Ui.SupplyMode, Mode=TwoWay}">
                        <ComboBox.ItemTemplate>
                            <DataTemplate>
                                <TextBlock Text="{Binding Converter={StaticResource EnumText}}" />
                            </DataTemplate>
                        </ComboBox.ItemTemplate>
                    </ComboBox>
                    <CheckBox Content="顺序循环" IsChecked="{Binding Ui.LoopSequence, Mode=TwoWay}"
                              VerticalAlignment="Center" Margin="12,0,0,0" />
                </StackPanel>

                <!-- 分隔线 -->
                <Rectangle Grid.Column="1" Width="1" Height="20" Fill="{DynamicResource BorderSubtle}" Margin="14,0" VerticalAlignment="Center" />

                <!-- 操作按钮 -->
                <StackPanel Grid.Column="2" Orientation="Horizontal" VerticalAlignment="Center">
                    <Button Content="执行供图" Command="{Binding ExecuteCommand}"
                            MinWidth="92" Height="30" Margin="0,0,8,0"
                            Style="{StaticResource OpenFilePlugin.PrimaryButtonStyle}" />
                    <Button Content="停止" Command="{Binding StopCommand}"
                            MinWidth="64" Height="30" />
                </StackPanel>

                <!-- 分隔线 -->
                <Rectangle Grid.Column="3" Width="1" Height="20" Fill="{DynamicResource BorderSubtle}" Margin="14,0" VerticalAlignment="Center" />

                <!-- 运行状态指示 -->
                <StackPanel Grid.Column="4" Orientation="Horizontal" VerticalAlignment="Center">
                    <Ellipse Width="8" Height="8" Fill="{DynamicResource StatusSuccess}" Margin="0,0,8,0" VerticalAlignment="Center" />
                    <TextBlock Text="{Binding Ui.StatusText, Mode=OneWay}"
                               VerticalAlignment="Center"
                               TextTrimming="CharacterEllipsis"
                               Foreground="{DynamicResource TextPrimary}" />
                </StackPanel>
            </Grid>
        </Border>
    </Grid>
</vb:ModuleViewBase>
```

---

### 文件 3: `Converters/Converters.cs`

- **相对路径**: `Converters/Converters.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `6.85 KB`
- **命名空间**: `Plugin.OpenFile.Converters`
- **核心类型**: `class FileTypeToIconConverter`, `class StatusToBrushConverter`, `class PreviewModeToVisibilityConverter`, `class EnumTextConverter`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Globalization;
using System.Windows;
using System.Windows.Data;
using System.Windows.Media;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.Converters
{
    /// <summary>文件类型 → 图标字符（避免图片资源依赖）。</summary>
    public class FileTypeToIconConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            if (!(value is FileKind))
            {
                return "📄";
            }
            switch ((FileKind)value)
            {
                case FileKind.Image: return "🖼";
                case FileKind.Markdown: return "📝";
                case FileKind.Csv: return "📊";
                case FileKind.Tsv: return "📊";
                case FileKind.Json: return "{}";
                case FileKind.HalconSource: return "⟨H⟩";
                case FileKind.Log: return "📃";
                default: return "📄";
            }
        }

        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            throw new NotSupportedException();
        }
    }

    /// <summary>
    /// 文件状态 → 语义色刷（优先宿主语义令牌 StatusSuccess/StatusDanger/StatusWarning，
    /// 实时主题刷新不保证——绑定值不变时不重查，README 已说明）。
    /// </summary>
    public class StatusToBrushConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            string text = value as string ?? string.Empty;
            if (text == "正常" || text == "已解析")
            {
                return ResolveBrush("StatusSuccess", "#FF1F9D55");
            }
            if (text == "缺失" || text == "解析失败")
            {
                return ResolveBrush("StatusDanger", "#FFE04B3A");
            }
            if (text == "损坏")
            {
                return ResolveBrush("StatusWarning", "#FFD9A514");
            }
            if (text == "已解析（截断）")
            {
                return ResolveBrush("StatusWarning", "#FFD9A514");
            }
            return ResolveBrush("TextSecondary", "#FF8A8A8A");
        }

        private static Brush ResolveBrush(string semanticKey, string fallbackHex)
        {
            var app = System.Windows.Application.Current;
            if (app != null)
            {
                var brush = app.TryFindResource(semanticKey) as Brush;
                if (brush != null)
                {
                    return brush;
                }
            }
            return new SolidColorBrush((Color)ColorConverter.ConvertFromString(fallbackHex));
        }

        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            throw new NotSupportedException();
        }
    }

    /// <summary>
    /// 预览模式 → 可见性（parameter = 模式名 Original/Table/Formatted/Rendered）。
    /// 供表格 DataGrid / 原文 TextBox / 格式化 TextBox / Markdown 渲染区切换显示。
    /// </summary>
    public class PreviewModeToVisibilityConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            var mode = value is DocumentPreviewMode ? (DocumentPreviewMode)value : DocumentPreviewMode.Original;
            string expect = parameter as string ?? "Original";
            DocumentPreviewMode target;
            switch (expect)
            {
                case "Table": target = DocumentPreviewMode.Table; break;
                case "Formatted": target = DocumentPreviewMode.Formatted; break;
                case "Rendered": target = DocumentPreviewMode.Rendered; break;
                default: target = DocumentPreviewMode.Original; break;
            }
            return mode == target ? Visibility.Visible : Visibility.Collapsed;
        }

        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            throw new NotSupportedException();
        }
    }

    /// <summary>枚举值 → 中文文本（供图模式/预览模式/导出选项 ComboBox ItemTemplate 单向显示）。</summary>
    public class EnumTextConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            // 模板标记（bool + ConverterParameter=template）
            if (value is bool && string.Equals(parameter as string, "template", StringComparison.OrdinalIgnoreCase))
            {
                return (bool)value ? "是（当前模板）" : "否";
            }
            if (value is ImageInputMode)
            {
                switch ((ImageInputMode)value)
                {
                    case ImageInputMode.CurrentImage: return "当前图像";
                    case ImageInputMode.Sequential: return "顺序供图";
                    case ImageInputMode.SequentialLoop: return "顺序循环";
                }
            }
            if (value is DocumentPreviewMode)
            {
                switch ((DocumentPreviewMode)value)
                {
                    case DocumentPreviewMode.Original: return "原文";
                    case DocumentPreviewMode.Table: return "表格";
                    case DocumentPreviewMode.Formatted: return "格式化";
                    case DocumentPreviewMode.Rendered: return "渲染";
                }
            }
            if (value is ExportScope)
            {
                switch ((ExportScope)value)
                {
                    case ExportScope.All: return "全部";
                    case ExportScope.Filtered: return "当前筛选";
                    case ExportScope.Selected: return "仅选中";
                }
            }
            if (value is FolderOrganizationMode)
            {
                switch ((FolderOrganizationMode)value)
                {
                    case FolderOrganizationMode.ByCategory: return "按类别分目录";
                    case FolderOrganizationMode.Flat: return "平铺";
                }
            }
            if (value is ExportConflictPolicy)
            {
                switch ((ExportConflictPolicy)value)
                {
                    case ExportConflictPolicy.Skip: return "跳过已存在";
                    case ExportConflictPolicy.Overwrite: return "覆盖";
                    case ExportConflictPolicy.Rename: return "自动重命名";
                }
            }
            return value != null ? value.ToString() : string.Empty;
        }

        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            throw new NotSupportedException();
        }
    }
}
```

---

### 文件 4: `Model/DocumentItemModel.cs`

- **相对路径**: `Model/DocumentItemModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.22 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class DocumentItemModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;

namespace Plugin.OpenFile.Model
{
    /// <summary>文档条目数据模型（文档 §6 DocumentItemModel）。只读预览，不修改源文件（文档 §3.3）。</summary>
    [Serializable]
    public class DocumentItemModel
    {
        public string Id { get; set; }

        public string SourcePath { get; set; }

        public string DisplayName { get; set; }

        public string Extension { get; set; }

        public long FileSize { get; set; }

        /// <summary>编码名称（"Auto" 表示自动识别，文档 §6）。</summary>
        public string EncodingName { get; set; }

        public FileKind DocumentType { get; set; }

        public DocumentParseStatus ParseStatus { get; set; }

        public string LastError { get; set; }

        public DocumentPreviewMode LastPreviewMode { get; set; }

        public DocumentItemModel()
        {
            Id = Guid.NewGuid().ToString("N");
            EncodingName = "Auto";
            DocumentType = FileKind.Unknown;
            ParseStatus = DocumentParseStatus.NotParsed;
            LastError = string.Empty;
            Extension = string.Empty;
            DisplayName = string.Empty;
            SourcePath = string.Empty;
        }
    }
}
```

---

### 文件 5: `Model/ExportSettings.cs`

- **相对路径**: `Model/ExportSettings.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.55 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class ExportSettings`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;

namespace Plugin.OpenFile.Model
{
    /// <summary>
    /// 样本导出配置（文档 §6 ExportSettings）。
    /// 默认策略：复制而非移动、不覆盖、按类别创建目录、生成 manifest.json、保留原始扩展名（文档 §6）。
    /// </summary>
    [Serializable]
    public class ExportSettings
    {
        public string TargetDirectory { get; set; }

        public ExportScope Scope { get; set; }

        public FolderOrganizationMode FolderMode { get; set; }

        /// <summary>是否包含未标注样本（默认 true，未标注落 "未标注" 目录）。</summary>
        public bool IncludeUnlabeled { get; set; }

        /// <summary>是否复制模板图像副本（落 "模板" 目录，文档阶段5）。</summary>
        public bool IncludeTemplateCopy { get; set; }

        public ExportConflictPolicy ConflictPolicy { get; set; }

        /// <summary>生成 manifest.json（默认开，文档 §6）。</summary>
        public bool WriteManifest { get; set; }

        /// <summary>导出时保留导入根目录相对路径结构。</summary>
        public bool PreserveRelativePath { get; set; }

        public ExportSettings()
        {
            TargetDirectory = string.Empty;
            Scope = ExportScope.All;
            FolderMode = FolderOrganizationMode.ByCategory;
            IncludeUnlabeled = true;
            IncludeTemplateCopy = false;
            ConflictPolicy = ExportConflictPolicy.Skip;
            WriteManifest = true;
            PreserveRelativePath = false;
        }
    }
}
```

---

### 文件 6: `Model/FileContracts.cs`

- **相对路径**: `Model/FileContracts.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.10 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class FileRecognitionResult`, `class FileParseRequest`, `class ImageMetadata`, `class ExportResultItem`, `class ExportResult`, `class ManifestEntry`, `class ExportManifest`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Threading;

namespace Plugin.OpenFile.Model
{
    /// <summary>文件识别结果（文档 §8 FileRecognitionService 返回值）。</summary>
    [Serializable]
    public class FileRecognitionResult
    {
        public FileKind Kind { get; set; }

        public string Extension { get; set; }

        public bool Exists { get; set; }

        public long FileSize { get; set; }

        public string ErrorMessage { get; set; }

        public FileRecognitionResult()
        {
            Extension = string.Empty;
            ErrorMessage = string.Empty;
        }
    }

    /// <summary>文档解析请求（文档 §8.5 FileParseRequest，含限量与取消）。</summary>
    [Serializable]
    public class FileParseRequest
    {
        public string FilePath { get; set; }

        /// <summary>"Auto" 或具体编码名。</summary>
        public string EncodingName { get; set; }

        public string Delimiter { get; set; }

        public bool HasHeader { get; set; }

        public int MaxBytes { get; set; }

        public int MaxLines { get; set; }

        public CancellationToken Token { get; set; }

        public FileParseRequest()
        {
            FilePath = string.Empty;
            EncodingName = "Auto";
            Delimiter = ",";
        }
    }

    /// <summary>图像元数据（Platform 适配层输出；不含 HALCON 对象）。</summary>
    [Serializable]
    public class ImageMetadata
    {
        public int Width { get; set; }

        public int Height { get; set; }

        public int Channels { get; set; }

        public string PixelType { get; set; }

        public ImageMetadata()
        {
            PixelType = string.Empty;
        }
    }

    /// <summary>单个样本导出结果。</summary>
    [Serializable]
    public class ExportResultItem
    {
        public string SourcePath { get; set; }

        public string TargetPath { get; set; }

        public string Category { get; set; }

        public bool IsTemplate { get; set; }

        public bool Success { get; set; }

        public bool Skipped { get; set; }

        public string Error { get; set; }

        public ExportResultItem()
        {
            SourcePath = string.Empty;
            TargetPath = string.Empty;
            Category = string.Empty;
            Error = string.Empty;
        }
    }

    /// <summary>导出汇总结果（文档阶段5：取消后成功/失败/未处理可区分）。</summary>
    [Serializable]
    public class ExportResult
    {
        public int SuccessCount { get; set; }

        public int SkipCount { get; set; }

        public int FailCount { get; set; }

        public bool Canceled { get; set; }

        public string ManifestPath { get; set; }

        public string SummaryText { get; set; }

        public System.Collections.Generic.List<ExportResultItem> Items { get; set; }

        public ExportResult()
        {
            ManifestPath = string.Empty;
            SummaryText = string.Empty;
            Items = new System.Collections.Generic.List<ExportResultItem>();
        }
    }

    /// <summary>manifest.json 条目。</summary>
    [Serializable]
    public class ManifestEntry
    {
        public string SourcePath { get; set; }

        public string TargetPath { get; set; }

        public string Category { get; set; }

        public bool IsTemplate { get; set; }

        public ManifestEntry()
        {
            SourcePath = string.Empty;
            TargetPath = string.Empty;
            Category = string.Empty;
        }
    }

    /// <summary>manifest.json 顶层结构。</summary>
    [Serializable]
    public class ExportManifest
    {
        public string CreatedAt { get; set; }

        public string Plugin { get; set; }

        public string TemplateImageId { get; set; }

        public System.Collections.Generic.List<ManifestEntry> Entries { get; set; }

        public ExportManifest()
        {
            CreatedAt = string.Empty;
            Plugin = "Plugin.OpenFile";
            TemplateImageId = string.Empty;
            Entries = new System.Collections.Generic.List<ManifestEntry>();
        }
    }
}
```

---

### 文件 7: `Model/FileEnums.cs`

- **相对路径**: `Model/FileEnums.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `3.04 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `enum ImageInputMode`, `enum FileKind`, `enum ImageFileStatus`, `enum DocumentParseStatus`, `enum ExportScope`, `enum FolderOrganizationMode`, `enum ExportConflictPolicy`, `enum DocumentPreviewMode`, `enum MarkdownBlockType`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 枚举定义文件

```csharp
using System;

namespace Plugin.OpenFile.Model
{
    /// <summary>图像供图模式（文档 §7.3：当前图像 / 顺序 / 顺序循环）。</summary>
    [Serializable]
    public enum ImageInputMode
    {
        /// <summary>每次执行发布当前选中图像。</summary>
        CurrentImage = 0,
        /// <summary>顺序供图，到末尾后报告序列结束（不复用上一张，文档阶段3验收）。</summary>
        Sequential = 1,
        /// <summary>顺序供图，到末尾后回到第一张（文档：循环供图默认关）。</summary>
        SequentialLoop = 2
    }

    /// <summary>文件识别类型（文档 §8：FileRecognitionService 返回）。</summary>
    [Serializable]
    public enum FileKind
    {
        Image = 0,
        Markdown = 1,
        Csv = 2,
        Tsv = 3,
        Text = 4,
        Log = 5,
        Json = 6,
        HalconSource = 7,
        Unknown = 8,
        Unsupported = 9
    }

    /// <summary>图像文件状态（文档 §6 ImageItemModel.FileStatus：缺失/损坏可诊断，不删除记录）。</summary>
    [Serializable]
    public enum ImageFileStatus
    {
        Ok = 0,
        Missing = 1,
        Damaged = 2,
        Unknown = 3
    }

    /// <summary>文档解析状态。</summary>
    [Serializable]
    public enum DocumentParseStatus
    {
        NotParsed = 0,
        Ok = 1,
        Failed = 2,
        Truncated = 3
    }

    /// <summary>导出范围（文档 §6 ExportSettings.ExportScope）。</summary>
    [Serializable]
    public enum ExportScope
    {
        /// <summary>全部图像。</summary>
        All = 0,
        /// <summary>当前筛选结果。</summary>
        Filtered = 1,
        /// <summary>仅选中项。</summary>
        Selected = 2
    }

    /// <summary>导出目录组织方式（文档 §6 FolderOrganizationMode）。</summary>
    [Serializable]
    public enum FolderOrganizationMode
    {
        /// <summary>按类别创建子目录。</summary>
        ByCategory = 0,
        /// <summary>平铺到同一目录。</summary>
        Flat = 1
    }

    /// <summary>导出冲突策略（默认：复制而非移动、不覆盖，文档阶段5验收）。</summary>
    [Serializable]
    public enum ExportConflictPolicy
    {
        /// <summary>跳过已存在文件。</summary>
        Skip = 0,
        /// <summary>覆盖已存在文件。</summary>
        Overwrite = 1,
        /// <summary>自动重命名。</summary>
        Rename = 2
    }

    /// <summary>文档预览模式（文档 §11.7：原文/表格/格式化/渲染）。</summary>
    [Serializable]
    public enum DocumentPreviewMode
    {
        Original = 0,
        Table = 1,
        Formatted = 2,
        Rendered = 3
    }

    /// <summary>Markdown 简化渲染块类型（Parsers 不依赖 WPF，由 View 层呈现）。</summary>
    [Serializable]
    public enum MarkdownBlockType
    {
        Paragraph = 0,
        Heading1 = 1,
        Heading2 = 2,
        Heading3 = 3,
        ListItem = 4,
        CodeBlock = 5,
        Quote = 6,
        Separator = 7
    }
}
```

---

### 文件 8: `Model/FilePreviewModel.cs`

- **相对路径**: `Model/FilePreviewModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `2.05 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class MarkdownBlock`, `class FilePreviewModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.Data;

namespace Plugin.OpenFile.Model
{
    /// <summary>Markdown 渲染块（Parsers 层输出，View 层呈现，保持 Parser 无 WPF 依赖）。</summary>
    [Serializable]
    public class MarkdownBlock
    {
        public MarkdownBlockType BlockType { get; set; }

        public string Text { get; set; }

        public MarkdownBlock()
        {
            Text = string.Empty;
        }

        public MarkdownBlock(MarkdownBlockType type, string text)
        {
            BlockType = type;
            Text = text ?? string.Empty;
        }
    }

    /// <summary>
    /// 文档预览结果模型（文档 §8 DocumentPreviewService 输出）。
    /// 原文/格式化/表格/渲染四类内容 + 截断与错误信息。
    /// DataTable 用于 CSV/TSV 表格绑定（System.Data，非控件，允许进入 Service 层输出）。
    /// </summary>
    [Serializable]
    public class FilePreviewModel
    {
        /// <summary>原文（限量读取后的文本）。</summary>
        public string OriginalText { get; set; }

        /// <summary>格式化文本（JSON 格式化 / CSV 转 Markdown）。</summary>
        public string FormattedText { get; set; }

        /// <summary>表格数据（CSV/TSV；无表数据为 null）。</summary>
        public DataTable PreviewTable { get; set; }

        /// <summary>Markdown 渲染块（Markdown 文件；其他为 null）。</summary>
        public List<MarkdownBlock> RenderBlocks { get; set; }

        public bool Truncated { get; set; }

        /// <summary>截断提示（含截断字节数/行数）。</summary>
        public string TruncatedText { get; set; }

        public string ErrorMessage { get; set; }

        public DocumentPreviewMode Mode { get; set; }

        public FilePreviewModel()
        {
            OriginalText = string.Empty;
            FormattedText = string.Empty;
            TruncatedText = string.Empty;
            ErrorMessage = string.Empty;
            Mode = DocumentPreviewMode.Original;
        }
    }
}
```

---

### 文件 9: `Model/ImageCategoryModel.cs`

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

- **相对路径**: `Model/ImageCategoryModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.71 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class ImageCategoryModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;

namespace Plugin.OpenFile.Model
{
    /// <summary>
    /// 图像类别模型（文档 §6 ImageCategoryModel）。
    /// 默认类别：未标注 / OK / NG（文档 §6）。
    /// 类别仅是样本管理标签，与算法检测结果解耦（文档 §11.5 / §17：分类与检测状态混淆是风险）。
    /// </summary>
    [Serializable]
    public class ImageCategoryModel
    {
        public string Id { get; set; }

        public string Name { get; set; }

        /// <summary>展示颜色（#RRGGBB 字符串，View 层解析为 Brush，避免序列化 WPF 对象）。</summary>
        public string DisplayColor { get; set; }

        public int SortIndex { get; set; }

        public bool IsBuiltIn { get; set; }

        public bool IsEnabled { get; set; }

        public ImageCategoryModel()
        {
        }

        public ImageCategoryModel(string id, string name, string displayColor, int sortIndex, bool isBuiltIn)
        {
            Id = id;
            Name = name;
            DisplayColor = displayColor;
            SortIndex = sortIndex;
            IsBuiltIn = isBuiltIn;
            IsEnabled = true;
        }

        /// <summary>创建默认内置类别：未标注 / OK / NG。</summary>
        public static ImageCategoryModel[] CreateDefaults()
        {
            return new[]
            {
                new ImageCategoryModel("cat-unlabeled", "未标注", "#FF8A8A8A", 0, true),
                new ImageCategoryModel("cat-ok", "OK", "#FF1F9D55", 1, true),
                new ImageCategoryModel("cat-ng", "NG", "#FFE04B3A", 2, true)
            };
        }

        public override string ToString()
        {
            return Name ?? string.Empty;
        }
    }
}
```

---

### 文件 10: `Model/ImageItemModel.cs`

- **相对路径**: `Model/ImageItemModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.92 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class ImageItemModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;

namespace Plugin.OpenFile.Model
{
    /// <summary>
    /// 图像条目数据模型（文档 §6 ImageItemModel）。
    /// 纯数据 + 可序列化；不保存 HObject/HImage/显示窗口/流（文档 §6 明令）。
    /// IsTemplate 不落盘，由 OpenFileSettings.TemplateImageId 推导（文档 §6）。
    /// </summary>
    [Serializable]
    public class ImageItemModel
    {
        /// <summary>稳定样本 ID（非列表索引，文档 §7.3：顺序模式用稳定 ID）。</summary>
        public string Id { get; set; }

        public string SourcePath { get; set; }

        public string DisplayName { get; set; }

        /// <summary>相对导入根目录的路径（用于导出时 PreserveRelativePath）。</summary>
        public string RelativePath { get; set; }

        public long FileSize { get; set; }

        public DateTime LastWriteTimeUtc { get; set; }

        public int Width { get; set; }

        public int Height { get; set; }

        public int Channels { get; set; }

        /// <summary>HALCON 像素类型（byte/uint2/real...）。</summary>
        public string PixelType { get; set; }

        /// <summary>类别 Id（默认 cat-unlabeled；旧项目缺类别时恢复为未标注，文档 §12.2）。</summary>
        public string CategoryId { get; set; }

        public string Remark { get; set; }

        public int ImportOrder { get; set; }

        public ImageFileStatus FileStatus { get; set; }

        public string LastError { get; set; }

        public ImageItemModel()
        {
            Id = Guid.NewGuid().ToString("N");
            CategoryId = "cat-unlabeled";
            FileStatus = ImageFileStatus.Unknown;
            PixelType = string.Empty;
            LastError = string.Empty;
            Remark = string.Empty;
            RelativePath = string.Empty;
            DisplayName = string.Empty;
            SourcePath = string.Empty;
        }
    }
}
```

---

### 文件 11: `Model/OpenFileSettings.cs`

- **相对路径**: `Model/OpenFileSettings.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.80 KB`
- **命名空间**: `Plugin.OpenFile.Model`
- **核心类型**: `class OpenFileSettings`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;

namespace Plugin.OpenFile.Model
{
    /// <summary>
    /// 插件持久化配置（文档 §6 OpenFileSettings / §12）。
    /// 只保存配置与清单数据；不保存 HALCON 对象、显示窗口、文档流、任务、取消源、WPF 控件（文档 §6 明令）。
    /// </summary>
    [Serializable]
    public class OpenFileSettings
    {
        /// <summary>配置架构版本（旧项目兼容迁移依据，文档 §12.3）。</summary>
        public int SchemaVersion { get; set; }

        /// <summary>供图模式。默认 CurrentImage；循环供图默认关（文档 §12.2）。</summary>
        public ImageInputMode ImageInputMode { get; set; }

        /// <summary>顺序供图是否循环（独立于模式开关，文档 §6 字段表；默认 false）。</summary>
        public bool LoopSequence { get; set; }

        /// <summary>文件夹导入是否递归扫描。</summary>
        public bool RecursiveFolderScan { get; set; }

        /// <summary>导入列表自然排序（1,2,10 而非 1,10,2）。</summary>
        public bool NaturalSort { get; set; }

        /// <summary>当前选中图像的稳定 ID。</summary>
        public string SelectedImageId { get; set; }

        /// <summary>模板图像的稳定 ID（单实例唯一模板，文档阶段4）。</summary>
        public string TemplateImageId { get; set; }

        /// <summary>当前筛选类别 Id（空 = 全部）。</summary>
        public string SelectedCategoryId { get; set; }

        /// <summary>文档编码（"Auto" = 自动识别，默认 UTF-8 自动识别，文档 §12.2）。</summary>
        public string DocumentEncoding { get; set; }

        /// <summary>CSV 分隔符（默认 ","）。</summary>
        public string CsvDelimiter { get; set; }

        /// <summary>CSV 是否含表头（默认 true）。</summary>
        public bool CsvHasHeader { get; set; }

        /// <summary>大文件限量预览：最大读取字节数（默认 2MB）。</summary>
        public int PreviewMaxBytes { get; set; }

        /// <summary>大文件限量预览：最大行数（默认 5000）。</summary>
        public int PreviewMaxLines { get; set; }

        public ExportSettings Export { get; set; }

        /// <summary>图像清单（持久化，文档 §12.1）。</summary>
        public List<ImageItemModel> ImageItems { get; set; }

        /// <summary>文档清单（持久化，文档 §12.1）。</summary>
        public List<DocumentItemModel> DocumentItems { get; set; }

        /// <summary>类别定义（持久化）。</summary>
        public List<ImageCategoryModel> Categories { get; set; }

        public OpenFileSettings()
        {
            SchemaVersion = 1;
            ImageInputMode = ImageInputMode.CurrentImage;
            LoopSequence = false;
            RecursiveFolderScan = false;
            NaturalSort = true;
            SelectedImageId = string.Empty;
            TemplateImageId = string.Empty;
            SelectedCategoryId = string.Empty;
            DocumentEncoding = "Auto";
            CsvDelimiter = ",";
            CsvHasHeader = true;
            PreviewMaxBytes = 2 * 1024 * 1024;
            PreviewMaxLines = 5000;
            Export = new ExportSettings();
            ImageItems = new List<ImageItemModel>();
            DocumentItems = new List<DocumentItemModel>();
            Categories = new List<ImageCategoryModel>(ImageCategoryModel.CreateDefaults());
        }

        /// <summary>反序列化后的缺省迁移（文档 §12.3：旧项目缺省字段补默认值，不伪装有效路径）。</summary>
        public void MigrateDefaults()
        {
            if (Export == null) Export = new ExportSettings();
            if (ImageItems == null) ImageItems = new List<ImageItemModel>();
            if (DocumentItems == null) DocumentItems = new List<DocumentItemModel>();
            if (Categories == null || Categories.Count == 0)
            {
                Categories = new List<ImageCategoryModel>(ImageCategoryModel.CreateDefaults());
            }
            if (string.IsNullOrEmpty(DocumentEncoding)) DocumentEncoding = "Auto";
            if (string.IsNullOrEmpty(CsvDelimiter)) CsvDelimiter = ",";
            if (PreviewMaxBytes <= 0) PreviewMaxBytes = 2 * 1024 * 1024;
            if (PreviewMaxLines <= 0) PreviewMaxLines = 5000;
            if (SelectedImageId == null) SelectedImageId = string.Empty;
            if (TemplateImageId == null) TemplateImageId = string.Empty;
            if (SelectedCategoryId == null) SelectedCategoryId = string.Empty;
            // 类别缺失的图像回退为未标注（文档 §12.3）
            foreach (var img in ImageItems)
            {
                if (img != null && string.IsNullOrEmpty(img.CategoryId)) img.CategoryId = "cat-unlabeled";
            }
        }
    }
}
```

---

### 文件 12: `Parsers/CsvParser.cs`

- **相对路径**: `Parsers/CsvParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `5.38 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `class CsvParser`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.IO;
using System.Text;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Services;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// CSV/TSV 解析（文档 §8.5 CsvParser）。
    /// 处理：引号包裹、双引号转义、字段内换行、空字段、前导零（保留文本格式，文档阶段6验收）。
    /// 输出 DataTable（文本列）+ Markdown 转换。
    /// </summary>
    public class CsvParser : IFileParser
    {
        public bool CanParse(FileRecognitionResult file)
        {
            return file != null && (file.Kind == FileKind.Csv || file.Kind == FileKind.Tsv);
        }

        public FilePreviewModel Parse(FileParseRequest request)
        {
            var model = new FilePreviewModel { Mode = DocumentPreviewMode.Original };
            bool truncated;
            string truncatedText;
            string text = TextFileParser.ReadTextLimited(request, out truncated, out truncatedText);
            model.OriginalText = text;
            model.Truncated = truncated;
            model.TruncatedText = truncatedText;

            string delimiter = request != null && !string.IsNullOrEmpty(request.Delimiter) ? request.Delimiter : ",";
            if (delimiter == "\\t") delimiter = "\t";
            bool hasHeader = request == null || request.HasHeader;

            model.PreviewTable = ToDataTable(text, delimiter, hasHeader);
            model.FormattedText = MarkdownParser.DataTableToMarkdown(model.PreviewTable, hasHeader);
            return model;
        }

        /// <summary>把 CSV 文本解析为 DataTable（全文本列，保留前导零）。</summary>
        public static DataTable ToDataTable(string text, string delimiter, bool hasHeader)
        {
            var table = new DataTable("Preview");
            if (string.IsNullOrEmpty(text) || string.IsNullOrEmpty(delimiter))
            {
                return table;
            }

            List<List<string>> rows = SplitRows(text, delimiter[0]);
            if (rows.Count == 0) return table;

            int colCount = 0;
            foreach (var row in rows)
            {
                if (row.Count > colCount) colCount = row.Count;
            }
            for (int c = 0; c < colCount; c++)
            {
                string name = hasHeader && rows[0].Count > c ? rows[0][c] : "列" + (c + 1);
                if (string.IsNullOrEmpty(name)) name = "列" + (c + 1);
                if (table.Columns.Contains(name)) name = name + "_" + c;
                table.Columns.Add(name, typeof(string));
            }

            int firstRow = hasHeader ? 1 : 0;
            for (int r = firstRow; r < rows.Count; r++)
            {
                var row = rows[r];
                var dataRow = table.NewRow();
                for (int c = 0; c < table.Columns.Count; c++)
                {
                    dataRow[c] = c < row.Count ? row[c] : string.Empty;
                }
                table.Rows.Add(dataRow);
            }
            return table;
        }

        /// <summary>RFC4180 风格分列：支持引号包裹字段、双引号转义、字段内换行。</summary>
        public static List<List<string>> SplitRows(string text, char delimiter)
        {
            var rows = new List<List<string>>();
            var current = new List<string>();
            var field = new StringBuilder();
            bool inQuotes = false;

            using (var reader = new StringReader(text))
            {
                int chInt;
                while ((chInt = reader.Read()) >= 0)
                {
                    char ch = (char)chInt;
                    if (inQuotes)
                    {
                        if (ch == '"')
                        {
                            int next = reader.Peek();
                            if (next == '"')
                            {
                                reader.Read();
                                field.Append('"');
                            }
                            else
                            {
                                inQuotes = false;
                            }
                        }
                        else
                        {
                            field.Append(ch);
                        }
                    }
                    else if (ch == '"')
                    {
                        inQuotes = true;
                    }
                    else if (ch == delimiter)
                    {
                        current.Add(field.ToString());
                        field.Length = 0;
                    }
                    else if (ch == '\n')
                    {
                        current.Add(field.ToString());
                        field.Length = 0;
                        rows.Add(current);
                        current = new List<string>();
                    }
                    else if (ch == '\r')
                    {
                        // 忽略，\n 触发行结束
                    }
                    else
                    {
                        field.Append(ch);
                    }
                }
                if (field.Length > 0 || current.Count > 0)
                {
                    current.Add(field.ToString());
                    rows.Add(current);
                }
            }
            return rows;
        }
    }
}
```

---

### 文件 13: `Parsers/HalconSourceParser.cs`

- **相对路径**: `Parsers/HalconSourceParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.06 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `class HalconSourceParser`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Services;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// HALCON 脚本源文件（.hdev/.hdvp）识别（文档 §8.5 HalconSourceParser）。
    /// 只做文本内容识别与原文预览，绝不执行（文档 §3.3 / 阶段6验收：HALCON 文件不会被执行）。
    /// </summary>
    public class HalconSourceParser : IFileParser
    {
        public bool CanParse(FileRecognitionResult file)
        {
            return file != null && file.Kind == FileKind.HalconSource;
        }

        public FilePreviewModel Parse(FileParseRequest request)
        {
            var model = new FilePreviewModel { Mode = DocumentPreviewMode.Original };
            bool truncated;
            string truncatedText;
            model.OriginalText = TextFileParser.ReadTextLimited(request, out truncated, out truncatedText);
            model.Truncated = truncated;
            model.TruncatedText = truncatedText;
            model.ErrorMessage = string.Empty;
            return model;
        }
    }
}
```

---

### 文件 14: `Parsers/IFileParser.cs`

- **相对路径**: `Parsers/IFileParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.56 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `interface IFileParser`, `class FileParserRegistry`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 接口定义文件

```csharp
using System.Collections.Generic;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// 文件解析器接口（文档 §8.5 IFileParser）。
    /// 文档中的 ParseAsync(FileParseRequest, CancellationToken) 异步语义由
    /// DocumentPreviewService 以 Task.Run 包装本接口的同步 Parse 实现（Parser 保持无 WPF/无任务依赖）。
    /// </summary>
    public interface IFileParser
    {
        /// <summary>是否支持该文件类型。</summary>
        bool CanParse(FileRecognitionResult file);

        /// <summary>执行解析，返回预览模型（含限量与错误信息）。</summary>
        FilePreviewModel Parse(FileParseRequest request);
    }

    /// <summary>解析器注册表（按 FileKind 分发）。</summary>
    public static class FileParserRegistry
    {
        private static readonly List<IFileParser> Parsers = new List<IFileParser>
        {
            new MarkdownParser(),
            new CsvParser(),
            new JsonParser(),
            new HalconSourceParser(),
            new TextFileParser()
        };

        /// <summary>按识别类型取解析器；无匹配返回 null（调用方回退原文展示）。</summary>
        public static IFileParser Resolve(FileKind kind)
        {
            var probe = new FileRecognitionResult { Kind = kind };
            foreach (var parser in Parsers)
            {
                if (parser.CanParse(probe))
                {
                    return parser;
                }
            }
            return null;
        }
    }
}
```

---

### 文件 15: `Parsers/JsonParser.cs`

- **相对路径**: `Parsers/JsonParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `5.40 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `class JsonParser`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;
using System.Web.Script.Serialization;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Services;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// JSON 解析（文档 §8.5 JsonParser）。
    /// 原文 + 格式化预览；解析失败时显示错误位置并保留原文（文档阶段6验收，非法 JSON 不崩溃）。
    /// 使用宿主已有依赖 System.Web.Extensions（JavaScriptSerializer），不新增包。
    /// </summary>
    public class JsonParser : IFileParser
    {
        public bool CanParse(FileRecognitionResult file)
        {
            return file != null && file.Kind == FileKind.Json;
        }

        public FilePreviewModel Parse(FileParseRequest request)
        {
            var model = new FilePreviewModel { Mode = DocumentPreviewMode.Original };
            bool truncated;
            string truncatedText;
            string text = TextFileParser.ReadTextLimited(request, out truncated, out truncatedText);
            model.OriginalText = text;
            model.Truncated = truncated;
            model.TruncatedText = truncatedText;

            object parsed;
            string error;
            if (TryParse(text, out parsed, out error))
            {
                model.FormattedText = Format(parsed, 0);
                model.ErrorMessage = string.Empty;
            }
            else
            {
                model.FormattedText = string.Empty;
                model.ErrorMessage = "JSON 解析失败：" + (error ?? "未知错误") + "（保留原文查看）";
            }
            return model;
        }

        /// <summary>解析 JSON；失败时返回 false 与错误描述。</summary>
        public static bool TryParse(string text, out object parsed, out string error)
        {
            parsed = null;
            error = string.Empty;
            if (string.IsNullOrWhiteSpace(text))
            {
                error = "内容为空";
                return false;
            }
            try
            {
                var serializer = new JavaScriptSerializer { MaxJsonLength = int.MaxValue };
                parsed = serializer.DeserializeObject(text);
                return true;
            }
            catch (ArgumentException ex)
            {
                error = ex.Message;
                return false;
            }
            catch (InvalidOperationException ex)
            {
                error = ex.Message;
                return false;
            }
        }

        /// <summary>把 JavaScriptSerializer 的 Dictionary/ArrayList 结构格式化为缩进 JSON 文本。</summary>
        public static string Format(object node, int indent)
        {
            var pad = new string(' ', indent * 2);
            var childPad = new string(' ', (indent + 1) * 2);
            if (node is IDictionary<string, object>)
            {
                var dict = (IDictionary<string, object>)node;
                if (dict.Count == 0) return "{}";
                var sb = new StringBuilder();
                sb.AppendLine("{");
                int i = 0;
                foreach (var kv in dict)
                {
                    sb.Append(childPad);
                    sb.Append(Quote(kv.Key));
                    sb.Append(": ");
                    sb.Append(Format(kv.Value, indent + 1));
                    if (i < dict.Count - 1) sb.Append(',');
                    sb.AppendLine();
                    i++;
                }
                sb.Append(pad).Append('}');
                return sb.ToString();
            }
            if (node is System.Collections.IEnumerable && !(node is string))
            {
                var list = new System.Collections.Generic.List<object>();
                foreach (var item in (System.Collections.IEnumerable)node) list.Add(item);
                if (list.Count == 0) return "[]";
                var sb = new StringBuilder();
                sb.AppendLine("[");
                for (int i = 0; i < list.Count; i++)
                {
                    sb.Append(childPad);
                    sb.Append(Format(list[i], indent + 1));
                    if (i < list.Count - 1) sb.Append(',');
                    sb.AppendLine();
                }
                sb.Append(pad).Append(']');
                return sb.ToString();
            }
            if (node is string) return Quote((string)node);
            if (node is bool) return ((bool)node) ? "true" : "false";
            if (node == null) return "null";
            return Convert.ToString(node, System.Globalization.CultureInfo.InvariantCulture);
        }

        private static string Quote(string s)
        {
            if (s == null) return "\"\"";
            var sb = new StringBuilder("\"");
            foreach (char c in s)
            {
                switch (c)
                {
                    case '"': sb.Append("\\\""); break;
                    case '\\': sb.Append("\\\\"); break;
                    case '\n': sb.Append("\\n"); break;
                    case '\r': sb.Append("\\r"); break;
                    case '\t': sb.Append("\\t"); break;
                    default:
                        if (c < ' ') sb.Append("\\u" + ((int)c).ToString("x4"));
                        else sb.Append(c);
                        break;
                }
            }
            sb.Append("\"");
            return sb.ToString();
        }
    }
}
```

---

### 文件 16: `Parsers/MarkdownParser.cs`

- **相对路径**: `Parsers/MarkdownParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `5.46 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `class MarkdownParser`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Services;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// Markdown 解析（文档 §8.5 MarkdownParser）：原文读取 + 简化结构化渲染块。
    /// 简化渲染支持：#/##/### 标题、- / * 列表、``` 代码块、> 引用、--- 分隔线、普通段落。
    /// 不引入第三方 Markdown 依赖（文档 §17：优先复用宿主依赖，不随意增加包）。
    /// </summary>
    public class MarkdownParser : IFileParser
    {
        public bool CanParse(FileRecognitionResult file)
        {
            return file != null && file.Kind == FileKind.Markdown;
        }

        public FilePreviewModel Parse(FileParseRequest request)
        {
            var model = new FilePreviewModel { Mode = DocumentPreviewMode.Original };
            bool truncated;
            string truncatedText;
            string text = TextFileParser.ReadTextLimited(request, out truncated, out truncatedText);
            model.OriginalText = text;
            model.Truncated = truncated;
            model.TruncatedText = truncatedText;
            model.RenderBlocks = BuildBlocks(text);
            model.FormattedText = string.Empty;
            return model;
        }

        /// <summary>把 Markdown 文本解析为渲染块列表（Parsers 层无 WPF 依赖）。</summary>
        public static List<MarkdownBlock> BuildBlocks(string text)
        {
            var blocks = new List<MarkdownBlock>();
            if (string.IsNullOrEmpty(text))
            {
                return blocks;
            }

            bool inCode = false;
            var codeBuffer = new List<string>();
            var lines = text.Replace("\r\n", "\n").Split('\n');
            foreach (var raw in lines)
            {
                string line = raw ?? string.Empty;
                if (line.TrimStart().StartsWith("```"))
                {
                    if (inCode)
                    {
                        blocks.Add(new MarkdownBlock(MarkdownBlockType.CodeBlock, string.Join(Environment.NewLine, codeBuffer.ToArray())));
                        codeBuffer.Clear();
                        inCode = false;
                    }
                    else
                    {
                        inCode = true;
                    }
                    continue;
                }
                if (inCode)
                {
                    codeBuffer.Add(line);
                    continue;
                }

                string t = line.TrimStart();
                if (t.StartsWith("###"))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Heading3, t.Substring(3).Trim()));
                }
                else if (t.StartsWith("##"))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Heading2, t.Substring(2).Trim()));
                }
                else if (t.StartsWith("#"))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Heading1, t.Substring(1).Trim()));
                }
                else if (t.StartsWith("- ") || t.StartsWith("* "))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.ListItem, t.Substring(2).Trim()));
                }
                else if (t.StartsWith(">"))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Quote, t.Substring(1).Trim()));
                }
                else if (t.StartsWith("---") || t.StartsWith("***"))
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Separator, string.Empty));
                }
                else if (t.Length > 0)
                {
                    blocks.Add(new MarkdownBlock(MarkdownBlockType.Paragraph, line.TrimEnd()));
                }
            }

            if (inCode && codeBuffer.Count > 0)
            {
                blocks.Add(new MarkdownBlock(MarkdownBlockType.CodeBlock, string.Join(Environment.NewLine, codeBuffer.ToArray())));
            }
            return blocks;
        }

        /// <summary>CSV 转 Markdown 表格文本（文档 §3.2：CSV 转 Markdown 预览或导出）。</summary>
        public static string DataTableToMarkdown(System.Data.DataTable table, bool hasHeader)
        {
            if (table == null) return string.Empty;
            var sb = new System.Text.StringBuilder();
            int colCount = table.Columns.Count;
            if (hasHeader)
            {
                var heads = new string[colCount];
                for (int i = 0; i < colCount; i++) heads[i] = EscapeCell(table.Columns[i].ColumnName);
                sb.AppendLine("| " + string.Join(" | ", heads) + " |");
                var sep = new string[colCount];
                for (int i = 0; i < colCount; i++) sep[i] = "---";
                sb.AppendLine("| " + string.Join(" | ", sep) + " |");
            }
            foreach (System.Data.DataRow row in table.Rows)
            {
                var cells = new string[colCount];
                for (int i = 0; i < colCount; i++) cells[i] = EscapeCell(Convert.ToString(row[i]));
                sb.AppendLine("| " + string.Join(" | ", cells) + " |");
            }
            return sb.ToString();
        }

        private static string EscapeCell(string cell)
        {
            if (string.IsNullOrEmpty(cell)) return string.Empty;
            return cell.Replace("|", "\\|").Replace("\r\n", " ").Replace("\n", " ");
        }
    }
}
```

---

### 文件 17: `Parsers/TextFileParser.cs`

- **相对路径**: `Parsers/TextFileParser.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.20 KB`
- **命名空间**: `Plugin.OpenFile.Parsers`
- **核心类型**: `class TextFileParser`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Services;

namespace Plugin.OpenFile.Parsers
{
    /// <summary>
    /// TXT/LOG 原文解析（文档 §8.5 TextFileParser）。
    /// 同时提供限量文本读取公共方法，供其他 Parser 复用（大文件不一次性无限加载，文档阶段6）。
    /// </summary>
    public class TextFileParser : IFileParser
    {
        public bool CanParse(FileRecognitionResult file)
        {
            return file != null && (file.Kind == FileKind.Text || file.Kind == FileKind.Log);
        }

        public FilePreviewModel Parse(FileParseRequest request)
        {
            var model = new FilePreviewModel { Mode = DocumentPreviewMode.Original };
            bool truncated;
            string truncatedText;
            model.OriginalText = ReadTextLimited(request, out truncated, out truncatedText);
            model.Truncated = truncated;
            model.TruncatedText = truncatedText;
            return model;
        }

        /// <summary>
        /// 限量读取文本：先按 maxBytes 截断字节流，再按 maxLines 截断行。
        /// 编码：encodingName 为 "Auto" 时自动识别，否则按名称解析。
        /// </summary>
        public static string ReadTextLimited(FileParseRequest request, out bool truncated, out string truncatedText)
        {
            truncated = false;
            truncatedText = string.Empty;
            if (request == null || string.IsNullOrEmpty(request.FilePath))
            {
                return string.Empty;
            }

            var info = new FileInfo(request.FilePath);
            if (!info.Exists)
            {
                truncatedText = "文件不存在";
                return string.Empty;
            }

            int byteLimit = request.MaxBytes > 0 ? request.MaxBytes : 2 * 1024 * 1024;
            int lineLimit = request.MaxLines > 0 ? request.MaxLines : 5000;
            bool truncatedByBytes = info.Length > byteLimit;
            int readLength = truncatedByBytes ? byteLimit : (int)Math.Min(info.Length, int.MaxValue);

            byte[] buffer = new byte[readLength];
            using (var fs = new FileStream(request.FilePath, FileMode.Open, FileAccess.Read, FileShare.ReadWrite))
            {
                int read = 0;
                while (read < readLength)
                {
                    int n = fs.Read(buffer, read, readLength - read);
                    if (n <= 0) break;
                    read += n;
                }
                if (read < buffer.Length)
                {
                    Array.Resize(ref buffer, read);
                }
            }

            Encoding encoding = EncodingDetectionService.Resolve(request.EncodingName, buffer);
            string text = encoding.GetString(buffer);
            if (text.Length > 0 && text[0] == '\uFEFF')
            {
                text = text.Substring(1);
            }

            // 行数限量
            var lines = new List<string>();
            var reader = new StringReader(text);
            string line;
            bool truncatedByLines = false;
            while ((line = reader.ReadLine()) != null)
            {
                if (lines.Count >= lineLimit)
                {
                    truncatedByLines = true;
                    break;
                }
                lines.Add(line);
            }

            if (truncatedByBytes || truncatedByLines)
            {
                truncated = true;
                string byBytes = truncatedByBytes ? ("字节超限(" + info.Length + ">" + byteLimit + ")") : null;
                string byLines = truncatedByLines ? ("行数超限(>" + lineLimit + ")") : null;
                truncatedText = "内容已截断：" + JoinParts(byBytes, byLines) + "，仅显示前 " + lines.Count + " 行";
                return string.Join(Environment.NewLine, lines.ToArray());
            }

            return text;
        }

        private static string JoinParts(string a, string b)
        {
            if (string.IsNullOrEmpty(a)) return b ?? string.Empty;
            if (string.IsNullOrEmpty(b)) return a;
            return a + "，" + b;
        }
    }
}
```

---

### 文件 18: `Platform/VmImagePlatformAdapter.cs`

- **相对路径**: `Platform/VmImagePlatformAdapter.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.58 KB`
- **命名空间**: `Plugin.OpenFile.Platform`
- **核心类型**: `interface IImagePlatformAdapter`, `class ImageMetadataProbe`, `class VmImagePlatformAdapter`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 接口定义文件

```csharp
using System;
using HalconDotNet;
using VM.Halcon;
using VM.Halcon.Config;
using VM.Halcon.Model;

namespace Plugin.OpenFile.Platform
{
    /// <summary>
    /// 平台图像适配接口（文档 §9 IImagePlatformAdapter 裁剪版）。
    /// 文档中的 CreatePreviewSource 由 ViewModel 层以 WPF 解码实现（不依赖 HALCON），
    /// 其余职责（LoadImage / GetImageMetadata / ReleaseImage）保持一致。
    /// </summary>
    public interface IImagePlatformAdapter
    {
        /// <summary>从文件加载图像为平台图像对象（插件拥有返回值）。</summary>
        RImage LoadImage(string path);

        /// <summary>读取图像元数据（不持有 HALCON 对象）。</summary>
        ImageMetadataProbe GetMetadata(string path);

        /// <summary>释放插件拥有的平台图像对象。</summary>
        void ReleaseImage(RImage image);
    }

    /// <summary>图像元数据探测结果（ImageMetadata 的平台层探测载体）。</summary>
    public class ImageMetadataProbe
    {
        public bool Success { get; set; }

        public string Error { get; set; }

        public int Width { get; set; }

        public int Height { get; set; }

        public int Channels { get; set; }

        public string PixelType { get; set; }

        public ImageMetadataProbe()
        {
            Error = string.Empty;
            PixelType = string.Empty;
        }
    }

    /// <summary>
    /// VM 平台图像适配实现。
    /// 证据链（全部来自参考插件源码 / 台账 confirmed by source）：
    ///  - HOperatorSet.ReadImage / GetImageSize / CountChannels / GetImageType：HALCON 标准静态签名；
    ///  - new RImage(hObject)：Plugin.GrabImage 源码实证（台账 §4）。
    /// </summary>
    public class VmImagePlatformAdapter : IImagePlatformAdapter
    {
        /// <summary>读图（调用方负责释放返回的 RImage）。</summary>
        public RImage LoadImage(string path)
        {
            HObject hObject = null;
            try
            {
                HOperatorSet.ReadImage(out hObject, path);
                if (hObject == null || !hObject.IsInitialized())
                {
                    throw new InvalidOperationException("图像读取失败或内容为空：" + path);
                }
                return new RImage(hObject);
            }
            finally
            {
                if (hObject != null)
                {
                    hObject.Dispose();
                }
            }
        }

        /// <summary>读元数据（宽/高/通道/像素类型）；失败时 Success=false + Error。</summary>
        public ImageMetadataProbe GetMetadata(string path)
        {
            var probe = new ImageMetadataProbe();
            HObject hObject = null;
            try
            {
                HOperatorSet.ReadImage(out hObject, path);
                if (hObject == null || !hObject.IsInitialized())
                {
                    probe.Error = "图像读取失败";
                    return probe;
                }
                HTuple width, height, channels, pixelType;
                HOperatorSet.GetImageSize(hObject, out width, out height);
                HOperatorSet.CountChannels(hObject, out channels);
                HOperatorSet.GetImageType(hObject, out pixelType);
                probe.Success = true;
                probe.Width = width.I;
                probe.Height = height.I;
                probe.Channels = channels.I;
                probe.PixelType = pixelType.S;
                return probe;
            }
            catch (HOperatorException ex)
            {
                // HOperatorException 的错误号 API 存在版本差异，统一用 Message（基类保证）
                probe.Error = "HALCON 错误：" + ex.Message;
                return probe;
            }
            catch (Exception ex)
            {
                probe.Error = ex.Message;
                return probe;
            }
            finally
            {
                if (hObject != null)
                {
                    hObject.Dispose();
                }
            }
        }

        /// <summary>释放插件拥有的图像（不释放借用的上游对象）。</summary>
        public void ReleaseImage(RImage image)
        {
            if (image != null)
            {
                try
                {
                    image.Dispose();
                }
                catch (Exception)
                {
                    // 释放失败不影响流程（对象可能已被平台接管）
                }
            }
        }
    }
}
```

---

### 文件 19: `Platform/VmOutputPublisher.cs`

- **相对路径**: `Platform/VmOutputPublisher.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.52 KB`
- **命名空间**: `Plugin.OpenFile.Platform`
- **核心类型**: `class OpenFileOutputBundle`, `interface IOutputPublisher`, `class VmOutputPublisher`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using HalconDotNet;
using VM.Halcon;
using VM.Halcon.Config;
using VM.Halcon.Model;
using VM.Start.Common.Const;
using VM.Start.Common.Enums;

namespace Plugin.OpenFile.Platform
{
    /// <summary>
    /// 输出快照（一个执行周期的全部输出值；失败周期字段回默认值，文档 §9.3 / §13.2）。
    /// </summary>
    public class OpenFileOutputBundle
    {
        public RImage Image { get; set; }

        public string ImagePath { get; set; }

        public string SampleId { get; set; }

        public string Category { get; set; }

        public int Width { get; set; }

        public int Height { get; set; }

        public int Channels { get; set; }

        public string PixelType { get; set; }

        public bool IsSequenceEnd { get; set; }

        public RImage TemplateImage { get; set; }

        public string TemplatePath { get; set; }

        public bool IsValid { get; set; }

        public string StatusCode { get; set; }

        public string StatusText { get; set; }

        public double ElapsedMs { get; set; }

        public OpenFileOutputBundle()
        {
            ImagePath = string.Empty;
            SampleId = string.Empty;
            Category = string.Empty;
            PixelType = string.Empty;
            TemplatePath = string.Empty;
            StatusCode = string.Empty;
            StatusText = string.Empty;
        }
    }

    /// <summary>输出发布接口（文档 §9 IOutputPublisher 裁剪版：路径/元数据/状态合并进 Publish）。</summary>
    public interface IOutputPublisher
    {
        /// <summary>把当前周期输出注册到平台（每个周期由 AddOutputParams 回调触发）。</summary>
        void Publish(OpenFileOutputBundle bundle, Action<string, string, object, string> addOutputParam);
    }

    /// <summary>
    /// VM 平台输出发布实现（封装 AddOutputParam 的语义类型注册与空图像兜底）。
    /// 语义类型对齐台账 §3：Image/String/Int/Bool/Double（禁止 CLR/HALCON 类名作为语义类型）。
    /// 有效图像以平台 RImage 发布；无图像时发布空 HImage，以保持图像输出槽位可链接。
    /// </summary>
    public class VmOutputPublisher : IOutputPublisher
    {
        public void Publish(OpenFileOutputBundle bundle, Action<string, string, object, string> addOutputParam)
        {
            if (bundle == null)
            {
                throw new ArgumentNullException(nameof(bundle));
            }
            if (addOutputParam == null)
            {
                throw new ArgumentNullException(nameof(addOutputParam));
            }

            object imageOutput = bundle.Image != null && bundle.Image.IsInitialized()
                ? (object)bundle.Image
                : new HImage();
            addOutputParam("图像", VariableTypes.Image, imageOutput, string.Empty);

            addOutputParam("图像路径", VariableTypes.String, bundle.ImagePath ?? string.Empty, string.Empty);
            addOutputParam("样本ID", VariableTypes.String, bundle.SampleId ?? string.Empty, string.Empty);
            addOutputParam("类别", VariableTypes.String, bundle.Category ?? string.Empty, string.Empty);
            addOutputParam("图像宽", VariableTypes.Int, bundle.Width, string.Empty);
            addOutputParam("图像高", VariableTypes.Int, bundle.Height, string.Empty);
            addOutputParam("通道数", VariableTypes.Int, bundle.Channels, string.Empty);
            addOutputParam("像素类型", VariableTypes.String, bundle.PixelType ?? string.Empty, string.Empty);
            addOutputParam("序列结束", VariableTypes.Bool, bundle.IsSequenceEnd, string.Empty);

            object templateImageOutput = bundle.TemplateImage != null && bundle.TemplateImage.IsInitialized()
                ? (object)bundle.TemplateImage
                : new HImage();
            addOutputParam("模板图像", VariableTypes.Image, templateImageOutput, string.Empty);
            addOutputParam("模板路径", VariableTypes.String, bundle.TemplatePath ?? string.Empty, string.Empty);

            // 诊断族（对齐《统一插件 UI 规范》建议字段）
            addOutputParam("IsValid", VariableTypes.Bool, bundle.IsValid, string.Empty);
            addOutputParam("StatusCode", VariableTypes.String, bundle.StatusCode ?? string.Empty, string.Empty);
            addOutputParam("StatusText", VariableTypes.String, bundle.StatusText ?? string.Empty, string.Empty);
            addOutputParam("耗时ms", VariableTypes.Double, bundle.ElapsedMs, string.Empty);
        }
    }
}
```

---

### 文件 20: `Properties/AssemblyInfo.cs`

- **相对路径**: `Properties/AssemblyInfo.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `726 B`
- **命名空间**: ``
- **核心类型**: `未识别`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: C# 源码文件，未识别到明确的类型定义

```csharp
using System.Reflection;
using System.Runtime.InteropServices;
using System.Windows;

[assembly: AssemblyTitle("Plugin.OpenFile")]
[assembly: AssemblyDescription("VM 平台文件导入插件：图像导入供图、模板示教样本管理、开发文档只读预览")]
[assembly: AssemblyConfiguration("")]
[assembly: AssemblyCompany("")]
[assembly: AssemblyProduct("Plugin.OpenFile")]
[assembly: AssemblyCopyright("Copyright © 2026")]
[assembly: AssemblyTrademark("")]
[assembly: AssemblyCulture("")]

[assembly: ComVisible(false)]

[assembly: ThemeInfo(
    ResourceDictionaryLocation.None,
    ResourceDictionaryLocation.SourceAssembly
)]

[assembly: AssemblyVersion("1.0.0.0")]
[assembly: AssemblyFileVersion("1.0.0.0")]
```

---

### 文件 21: `Services/DocumentPreviewService.cs`

- **相对路径**: `Services/DocumentPreviewService.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `2.61 KB`
- **命名空间**: `Plugin.OpenFile.Services`
- **核心类型**: `class DocumentPreviewService`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 业务服务或业务逻辑相关代码

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

```csharp
using System;
using System.Threading;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Parsers;

namespace Plugin.OpenFile.Services
{
    /// <summary>
    /// 文档预览服务（文档 §8 DocumentPreviewService）。
    /// 读文本 → 识编码 → 限大小 → 调 Parser → 生成预览。
    /// 同步实现；ViewModel 以请求 ID + Task.Run 包装防旧请求覆盖新预览（文档 §17 风险表）。
    /// </summary>
    public static class DocumentPreviewService
    {
        /// <summary>执行预览：按类型分发到 Parser；无专用 Parser 时回退原文读取。</summary>
        public static FilePreviewModel Preview(string path, FileKind kind, string encodingName, string csvDelimiter,
            bool csvHasHeader, int maxBytes, int maxLines, CancellationToken token)
        {
            var request = new FileParseRequest
            {
                FilePath = path,
                EncodingName = encodingName,
                Delimiter = string.Equals(kind, FileKind.Tsv) && string.IsNullOrEmpty(csvDelimiter) ? "\t" : csvDelimiter,
                HasHeader = csvHasHeader,
                MaxBytes = maxBytes,
                MaxLines = maxLines,
                Token = token
            };

            string permissionError;
            if (!FileRecognitionService.CheckReadable(path, out permissionError))
            {
                return new FilePreviewModel { ErrorMessage = permissionError };
            }

            try
            {
                token.ThrowIfCancellationRequested();
                IFileParser parser = FileParserRegistry.Resolve(kind);
                if (parser != null)
                {
                    return parser.Parse(request);
                }
                return ReadTextLimited(request);
            }
            catch (OperationCanceledException)
            {
                throw;
            }
            catch (Exception ex)
            {
                return new FilePreviewModel { ErrorMessage = "预览失败：" + ex.Message };
            }
        }

        /// <summary>无专用 Parser 时的原文限量读取。</summary>
        private static FilePreviewModel ReadTextLimited(FileParseRequest request)
        {
            bool truncated;
            string truncatedText;
            string text = TextFileParser.ReadTextLimited(request, out truncated, out truncatedText);
            return new FilePreviewModel
            {
                OriginalText = text,
                Truncated = truncated,
                TruncatedText = truncatedText,
                Mode = DocumentPreviewMode.Original
            };
        }
    }
}
```

---

### 文件 22: `Services/EncodingDetectionService.cs`

- **相对路径**: `Services/EncodingDetectionService.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `2.26 KB`
- **命名空间**: `Plugin.OpenFile.Services`
- **核心类型**: `class EncodingDetectionService`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 业务服务或业务逻辑相关代码

```csharp
using System;
using System.Text;

namespace Plugin.OpenFile.Services
{
    /// <summary>
    /// 文本编码检测（文档 §8 EncodingDetectionService）。
    /// 策略：BOM 优先 → UTF-8 严格解码校验 → 失败回退 GB18030。
    /// </summary>
    public static class EncodingDetectionService
    {
        /// <summary>按名称解析编码；"Auto" 时自动检测；名称无效时回退 UTF-8。</summary>
        public static Encoding Resolve(string encodingName, byte[] bytes)
        {
            if (!string.IsNullOrEmpty(encodingName) && !string.Equals(encodingName, "Auto", StringComparison.OrdinalIgnoreCase))
            {
                try
                {
                    return Encoding.GetEncoding(encodingName);
                }
                catch (ArgumentException)
                {
                    // 未知编码名 → 走自动检测
                }
            }
            return Detect(bytes);
        }

        /// <summary>BOM + UTF-8 严格校验 + GB18030 回退。</summary>
        public static Encoding Detect(byte[] bytes)
        {
            if (bytes == null || bytes.Length == 0)
            {
                return new UTF8Encoding(false);
            }
            if (bytes.Length >= 3 && bytes[0] == 0xEF && bytes[1] == 0xBB && bytes[2] == 0xBF)
            {
                return new UTF8Encoding(true);
            }
            if (bytes.Length >= 2 && bytes[0] == 0xFF && bytes[1] == 0xFE)
            {
                return Encoding.Unicode;
            }
            if (bytes.Length >= 2 && bytes[0] == 0xFE && bytes[1] == 0xFF)
            {
                return Encoding.BigEndianUnicode;
            }

            // 无 BOM：严格 UTF-8 校验（allowInvalid=false），失败按 GB18030
            try
            {
                var strict = new UTF8Encoding(false, true);
                strict.GetString(bytes);
                return new UTF8Encoding(false);
            }
            catch (DecoderFallbackException)
            {
                try
                {
                    return Encoding.GetEncoding("GB18030");
                }
                catch (ArgumentException)
                {
                    return Encoding.Default;
                }
            }
        }
    }
}
```

---

### 文件 23: `Services/FileRecognitionService.cs`

- **相对路径**: `Services/FileRecognitionService.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `3.50 KB`
- **命名空间**: `Plugin.OpenFile.Services`
- **核心类型**: `class FileRecognitionService`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 业务服务或业务逻辑相关代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.Services
{
    /// <summary>
    /// 文件识别服务（文档 §8 FileRecognitionService）。
    /// 按扩展名初筛 → 存在性检查 → 读取权限检查；返回 FileRecognitionResult。
    /// </summary>
    public static class FileRecognitionService
    {
        /// <summary>支持的图像扩展名（文档阶段2验收：PNG/JPG/BMP/TIFF 至少验证）。</summary>
        public static readonly string[] ImageExtensions = { ".png", ".jpg", ".jpeg", ".bmp", ".tif", ".tiff" };

        private static readonly string[] MarkdownExtensions = { ".md", ".markdown" };
        private static readonly string[] HalconExtensions = { ".hdev", ".hdvp" };

        /// <summary>是否为受支持图像扩展名。</summary>
        public static bool IsImageExtension(string extension)
        {
            if (string.IsNullOrEmpty(extension)) return false;
            string ext = extension.ToLowerInvariant();
            foreach (var item in ImageExtensions)
            {
                if (item == ext) return true;
            }
            return false;
        }

        /// <summary>识别文件类型（扩展名初筛，不做内容解码）。</summary>
        public static FileKind RecognizeKind(string path)
        {
            string ext = (Path.GetExtension(path) ?? string.Empty).ToLowerInvariant();
            if (IsImageExtension(ext)) return FileKind.Image;
            foreach (var item in MarkdownExtensions) if (item == ext) return FileKind.Markdown;
            if (ext == ".csv") return FileKind.Csv;
            if (ext == ".tsv") return FileKind.Tsv;
            if (ext == ".txt") return FileKind.Text;
            if (ext == ".log") return FileKind.Log;
            if (ext == ".json") return FileKind.Json;
            foreach (var item in HalconExtensions) if (item == ext) return FileKind.HalconSource;
            if (ext == ".md" || ext == ".json" || ext == ".hdev") return FileKind.Unknown;
            return FileKind.Unsupported;
        }

        /// <summary>识别 + 存在/大小检查。</summary>
        public static FileRecognitionResult Recognize(string path)
        {
            var result = new FileRecognitionResult
            {
                Kind = RecognizeKind(path),
                Extension = (Path.GetExtension(path) ?? string.Empty).ToLowerInvariant()
            };
            try
            {
                var info = new FileInfo(path);
                result.Exists = info.Exists;
                if (info.Exists)
                {
                    result.FileSize = info.Length;
                }
                else
                {
                    result.ErrorMessage = "文件不存在";
                }
            }
            catch (Exception ex)
            {
                result.Exists = false;
                result.ErrorMessage = "访问失败：" + ex.Message;
            }
            return result;
        }

        /// <summary>读取权限检查（E04：无访问权限可诊断）。</summary>
        public static bool CheckReadable(string path, out string error)
        {
            error = string.Empty;
            try
            {
                using (File.OpenRead(path))
                {
                    return true;
                }
            }
            catch (Exception ex)
            {
                error = "无读取权限：" + ex.Message;
                return false;
            }
        }
    }
}
```

---

### 文件 24: `Services/ImageImportService.cs`

- **相对路径**: `Services/ImageImportService.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `5.85 KB`
- **命名空间**: `Plugin.OpenFile.Services`
- **核心类型**: `class ImageImportService`, `class NaturalFileComparer`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 业务服务或业务逻辑相关代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Runtime.InteropServices;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.Services
{
    /// <summary>
    /// 图像导入服务（文档 §8 ImageImportService）。
    /// 扫描文件/目录 → 扩展名过滤 → 自然排序 → 去重 → 读文件系统信息。
    /// 不读取 HALCON 元数据（宽高/通道/像素类型延迟到预览与供图时更新，避免大批量导入卡顿）；
    /// 不直接操作 WPF 控件或 ViewModel（文档 §8 约束）。
    /// </summary>
    public static class ImageImportService
    {
        /// <summary>导入多个文件（单图/多图；过滤不支持与重复项）。</summary>
        public static List<ImageItemModel> ImportFiles(IEnumerable<string> paths, int startOrder, List<string> existingPaths)
        {
            var imported = new List<ImageItemModel>();
            if (paths == null) return imported;
            var seen = BuildPathSet(existingPaths);
            int order = startOrder;

            foreach (var path in paths)
            {
                if (string.IsNullOrWhiteSpace(path)) continue;
                var kind = FileRecognitionService.RecognizeKind(path);
                if (kind != FileKind.Image) continue;
                var normalized = Path.GetFullPath(path);
                if (seen.ContainsKey(normalized)) continue;
                seen[normalized] = true;
                imported.Add(CreateItem(normalized, order++));
            }
            return imported;
        }

        /// <summary>导入文件夹（可递归；excludeDirs 用于排除导出目标目录，避免递归导入，文档 §17 风险表）。</summary>
        public static List<ImageItemModel> ImportFolder(string folder, bool recursive, int startOrder, List<string> existingPaths, IEnumerable<string> excludeDirs)
        {
            var imported = new List<ImageItemModel>();
            if (string.IsNullOrWhiteSpace(folder) || !Directory.Exists(folder)) return imported;

            var seen = BuildPathSet(existingPaths);
            var excludes = (excludeDirs ?? new string[0])
                .Where(d => !string.IsNullOrEmpty(d))
                .Select(d => Path.GetFullPath(d).TrimEnd(Path.DirectorySeparatorChar) + Path.DirectorySeparatorChar)
                .ToList();

            var option = recursive ? SearchOption.AllDirectories : SearchOption.TopDirectoryOnly;
            string[] files;
            try
            {
                files = Directory.GetFiles(folder, "*.*", option);
            }
            catch (Exception)
            {
                return imported;
            }

            int order = startOrder;
            foreach (var path in files.OrderBy(p => p, new NaturalFileComparer()))
            {
                if (!FileRecognitionService.IsImageExtension(Path.GetExtension(path))) continue;
                string normalized;
                try
                {
                    normalized = Path.GetFullPath(path);
                }
                catch (Exception)
                {
                    continue;
                }

                bool excluded = false;
                foreach (var prefix in excludes)
                {
                    if (normalized.StartsWith(prefix, StringComparison.OrdinalIgnoreCase))
                    {
                        excluded = true;
                        break;
                    }
                }
                if (excluded) continue;
                if (seen.ContainsKey(normalized)) continue;
                seen[normalized] = true;
                imported.Add(CreateItem(normalized, order++));
            }
            return imported;
        }

        private static ImageItemModel CreateItem(string fullPath, int order)
        {
            var info = new FileInfo(fullPath);
            var item = new ImageItemModel
            {
                SourcePath = fullPath,
                DisplayName = info.Name,
                FileSize = info.Exists ? info.Length : 0,
                LastWriteTimeUtc = info.Exists ? info.LastWriteTimeUtc : DateTime.MinValue,
                ImportOrder = order,
                FileStatus = info.Exists ? ImageFileStatus.Ok : ImageFileStatus.Missing
            };
            return item;
        }

        private static Dictionary<string, bool> BuildPathSet(List<string> existingPaths)
        {
            var set = new Dictionary<string, bool>(StringComparer.OrdinalIgnoreCase);
            if (existingPaths == null) return set;
            foreach (var p in existingPaths)
            {
                if (string.IsNullOrEmpty(p)) continue;
                try
                {
                    set[Path.GetFullPath(p)] = true;
                }
                catch (Exception)
                {
                    // 非法路径跳过
                }
            }
            return set;
        }
    }

    /// <summary>
    /// 自然排序比较器（"img2" &lt; "img10"）。
    /// 优先使用系统 StrCmpLogicalW（资源管理器同款）；P/Invoke 失败回退普通比较。
    /// </summary>
    public class NaturalFileComparer : IComparer<string>
    {
        [DllImport("shlwapi.dll", CharSet = CharSet.Unicode)]
        private static extern int StrCmpLogicalW(string x, string y);

        private static bool _nativeBroken;

        public int Compare(string x, string y)
        {
            if (x == y) return 0;
            if (x == null) return -1;
            if (y == null) return 1;
            if (!_nativeBroken)
            {
                try
                {
                    return StrCmpLogicalW(x, y);
                }
                catch (Exception)
                {
                    _nativeBroken = true;
                }
            }
            return string.Compare(x, y, StringComparison.OrdinalIgnoreCase);
        }
    }
}
```

---

### 文件 25: `Services/SampleExportService.cs`

- **相对路径**: `Services/SampleExportService.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `9.42 KB`
- **命名空间**: `Plugin.OpenFile.Services`
- **核心类型**: `class SampleExportService`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 业务服务或业务逻辑相关代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Threading;
using System.Web.Script.Serialization;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.Services
{
    /// <summary>
    /// 样本导出服务（文档 §8 SampleExportService）。
    /// 固定快照 → 建目录 → 复制（默认不覆盖）→ 冲突处理 → 取消支持 → manifest.json。
    /// 默认只复制、不移动、不修改源文件（文档阶段5验收）。
    /// </summary>
    public static class SampleExportService
    {
        /// <summary>
        /// 执行导出。
        /// </summary>
        /// <param name="snapshot">导出范围图像快照（调用方锁定后构建）。</param>
        /// <param name="templateItem">模板图像（可为 null；IncludeTemplateCopy 时复制副本）。</param>
        /// <param name="categoryNames">类别 Id → 名称映射。</param>
        /// <param name="settings">导出配置。</param>
        /// <param name="token">取消令牌。</param>
        /// <param name="progress">进度回调（已复制数）。</param>
        public static ExportResult Export(List<ImageItemModel> snapshot, ImageItemModel templateItem,
            Dictionary<string, string> categoryNames, ExportSettings settings, CancellationToken token,
            IProgress<int> progress)
        {
            var result = new ExportResult();
            if (settings == null || string.IsNullOrWhiteSpace(settings.TargetDirectory))
            {
                result.SummaryText = "导出失败：未设置目标目录";
                return result;
            }

            string root;
            try
            {
                root = Path.GetFullPath(settings.TargetDirectory);
                Directory.CreateDirectory(root);
            }
            catch (Exception ex)
            {
                result.SummaryText = "导出失败：目标目录不可用（" + ex.Message + "）";
                return result;
            }

            // 固定快照（文档 §8：导出基于导入快照，不随 UI 变化）
            var items = snapshot ?? new List<ImageItemModel>();
            int total = items.Count + (settings.IncludeTemplateCopy && templateItem != null ? 1 : 0);
            int done = 0;

            foreach (var item in items)
            {
                if (token.IsCancellationRequested)
                {
                    result.Canceled = true;
                    break;
                }

                string category = item == null ? "未知" : ResolveCategoryName(item.CategoryId, categoryNames);
                if (item != null && string.Equals(item.CategoryId, "cat-unlabeled") && !settings.IncludeUnlabeled)
                {
                    result.SkipCount++;
                    done++;
                    if (progress != null) progress.Report(done);
                    continue;
                }

                var entry = CopyOne(item, category, false, root, categoryNames, settings);
                if (entry.Success) result.SuccessCount++;
                else if (entry.Skipped) result.SkipCount++;
                else result.FailCount++;
                result.Items.Add(entry);

                done++;
                if (progress != null) progress.Report(done);
            }

            if (!result.Canceled && settings.IncludeTemplateCopy && templateItem != null)
            {
                var entry = CopyOne(templateItem, "模板", true, root, categoryNames, settings);
                if (entry.Success) result.SuccessCount++;
                else if (entry.Skipped) result.SkipCount++;
                else result.FailCount++;
                result.Items.Add(entry);
                done++;
                if (progress != null) progress.Report(done);
            }

            if (!result.Canceled && settings.WriteManifest && result.Items.Count > 0)
            {
                result.ManifestPath = WriteManifest(root, templateItem, result.Items);
            }

            result.SummaryText = (result.Canceled ? "导出已取消。" : "导出完成。")
                + "成功 " + result.SuccessCount + "，跳过 " + result.SkipCount + "，失败 " + result.FailCount
                + (string.IsNullOrEmpty(result.ManifestPath) ? "" : "，清单：" + result.ManifestPath);
            return result;
        }

        private static ExportResultItem CopyOne(ImageItemModel item, string categoryName, bool isTemplate,
            string root, Dictionary<string, string> categoryNames, ExportSettings settings)
        {
            var entry = new ExportResultItem
            {
                SourcePath = item != null ? item.SourcePath : string.Empty,
                Category = categoryName,
                IsTemplate = isTemplate
            };
            if (item == null || string.IsNullOrEmpty(item.SourcePath))
            {
                entry.Error = "空条目";
                return entry;
            }
            try
            {
                string dir = settings.FolderMode == FolderOrganizationMode.ByCategory
                    ? Path.Combine(root, MakeSafeDirName(categoryName))
                    : root;
                Directory.CreateDirectory(dir);

                string targetName;
                if (settings.PreserveRelativePath && !isTemplate && !string.IsNullOrEmpty(item.RelativePath))
                {
                    string relativeDir = Path.GetDirectoryName(item.RelativePath);
                    if (!string.IsNullOrEmpty(relativeDir))
                    {
                        dir = Path.Combine(dir, MakeSafeDirName(relativeDir));
                        Directory.CreateDirectory(dir);
                    }
                    targetName = Path.GetFileName(item.SourcePath);
                }
                else
                {
                    targetName = Path.GetFileName(item.SourcePath);
                }

                string target = Path.Combine(dir, targetName);

                if (File.Exists(target))
                {
                    switch (settings.ConflictPolicy)
                    {
                        case ExportConflictPolicy.Skip:
                            entry.TargetPath = target;
                            entry.Skipped = true;
                            return entry;
                        case ExportConflictPolicy.Overwrite:
                            break;
                        case ExportConflictPolicy.Rename:
                        default:
                            target = BuildRenamedPath(dir, targetName);
                            break;
                    }
                }

                File.Copy(item.SourcePath, target, settings.ConflictPolicy == ExportConflictPolicy.Overwrite);
                entry.TargetPath = target;
                entry.Success = true;
                return entry;
            }
            catch (Exception ex)
            {
                entry.Error = ex.Message;
                return entry;
            }
        }

        private static string BuildRenamedPath(string dir, string fileName)
        {
            string name = Path.GetFileNameWithoutExtension(fileName);
            string ext = Path.GetExtension(fileName);
            for (int i = 1; i < 10000; i++)
            {
                string candidate = Path.Combine(dir, name + "_" + i + ext);
                if (!File.Exists(candidate)) return candidate;
            }
            return Path.Combine(dir, Guid.NewGuid().ToString("N") + ext);
        }

        private static string MakeSafeDirName(string name)
        {
            if (string.IsNullOrEmpty(name)) return "未分类";
            var invalid = Path.GetInvalidFileNameChars();
            var chars = name.Select(c => invalid.Contains(c) ? '_' : c).ToArray();
            string safe = new string(chars).Trim();
            return string.IsNullOrEmpty(safe) ? "未分类" : safe;
        }

        private static string WriteManifest(string root, ImageItemModel templateItem, List<ExportResultItem> items)
        {
            try
            {
                var manifest = new ExportManifest
                {
                    CreatedAt = DateTime.Now.ToString("yyyy-MM-dd HH:mm:ss"),
                    TemplateImageId = templateItem != null ? templateItem.Id : string.Empty
                };
                foreach (var item in items)
                {
                    manifest.Entries.Add(new ManifestEntry
                    {
                        SourcePath = item.SourcePath,
                        TargetPath = item.TargetPath,
                        Category = item.Category,
                        IsTemplate = item.IsTemplate
                    });
                }
                var serializer = new JavaScriptSerializer { MaxJsonLength = int.MaxValue };
                string json = serializer.Serialize(manifest);
                string path = Path.Combine(root, "manifest.json");
                File.WriteAllText(path, json, new System.Text.UTF8Encoding(true));
                return path;
            }
            catch (Exception)
            {
                return string.Empty;
            }
        }

        private static string ResolveCategoryName(string categoryId, Dictionary<string, string> categoryNames)
        {
            if (categoryNames != null && !string.IsNullOrEmpty(categoryId) && categoryNames.ContainsKey(categoryId))
            {
                return categoryNames[categoryId];
            }
            return "未标注";
        }
    }
}
```

---

### 文件 26: `ViewModels/DocumentItemViewModel.cs`

- **相对路径**: `ViewModels/DocumentItemViewModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `2.85 KB`
- **命名空间**: `Plugin.OpenFile.ViewModels`
- **核心类型**: `class DocumentItemViewModel`
- **依赖摘要**: `DocumentItemModel`
- **概要**: WPF/MVVM 视图模型相关代码

```csharp
using System;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.ViewModels
{
    /// <summary>文档条目包装 ViewModel（文档 §7 DocumentItemViewModel）。</summary>
    public class DocumentItemViewModel : ObservableObject
    {
        private readonly DocumentItemModel _model;

        public DocumentItemViewModel(DocumentItemModel model)
        {
            _model = model ?? throw new ArgumentNullException("model");
        }

        public DocumentItemModel Model
        {
            get { return _model; }
        }

        public string Id
        {
            get { return _model.Id; }
        }

        public string SourcePath
        {
            get { return _model.SourcePath; }
        }

        public string DisplayName
        {
            get { return _model.DisplayName; }
        }

        public string Extension
        {
            get { return _model.Extension; }
        }

        public string EncodingName
        {
            get { return _model.EncodingName; }
        }

        public string TypeText
        {
            get
            {
                switch (_model.DocumentType)
                {
                    case FileKind.Markdown: return "Markdown";
                    case FileKind.Csv: return "CSV";
                    case FileKind.Tsv: return "TSV";
                    case FileKind.Text: return "TXT";
                    case FileKind.Log: return "LOG";
                    case FileKind.Json: return "JSON";
                    case FileKind.HalconSource: return "HALCON 脚本";
                    default: return "未知";
                }
            }
        }

        public string SizeText
        {
            get
            {
                if (_model.FileSize >= 1024 * 1024)
                {
                    return (_model.FileSize / (1024.0 * 1024.0)).ToString("F1") + " MB";
                }
                if (_model.FileSize >= 1024)
                {
                    return (_model.FileSize / 1024.0).ToString("F1") + " KB";
                }
                return _model.FileSize + " B";
            }
        }

        public string StatusText
        {
            get
            {
                switch (_model.ParseStatus)
                {
                    case DocumentParseStatus.Ok: return "已解析";
                    case DocumentParseStatus.Truncated: return "已解析（截断）";
                    case DocumentParseStatus.Failed: return "解析失败";
                    default: return "未解析";
                }
            }
        }

        /// <summary>解析状态/编码变更后由 VM 调用。</summary>
        public void RefreshStatus()
        {
            OnPropertyChanged("StatusText");
            OnPropertyChanged("TypeText");
            OnPropertyChanged("SizeText");
            OnPropertyChanged("EncodingName");
        }
    }
}
```

---

### 文件 27: `ViewModels/ImageItemViewModel.cs`

- **相对路径**: `ViewModels/ImageItemViewModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.99 KB`
- **命名空间**: `Plugin.OpenFile.ViewModels`
- **核心类型**: `class ImageItemViewModel`
- **依赖摘要**: `ImageItemModel`
- **概要**: WPF/MVVM 视图模型相关代码

```csharp
using System;
using System.IO;
using System.Windows.Media.Imaging;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.ViewModels
{
    /// <summary>
    /// 图像条目包装 ViewModel（文档 §7 ImageItemViewModel）。
    /// 缩略图用 WPF 延迟小尺寸解码（96px，不使用 HALCON，无界内存风险可控）；
    /// 元数据（宽/高/通道/像素类型）延迟到预览/供图时由 VM 填充后调用 RefreshMetadata。
    /// </summary>
    public class ImageItemViewModel : ObservableObject
    {
        private readonly ImageItemModel _model;
        private BitmapSource _thumbnail;
        private bool _thumbnailFailed;
        private bool _isTemplate;

        public ImageItemViewModel(ImageItemModel model)
        {
            _model = model ?? throw new ArgumentNullException("model");
        }

        public ImageItemModel Model
        {
            get { return _model; }
        }

        public string Id
        {
            get { return _model.Id; }
        }

        public string SourcePath
        {
            get { return _model.SourcePath; }
        }

        public string DisplayName
        {
            get { return _model.DisplayName; }
        }

        public string CategoryId
        {
            get { return _model.CategoryId; }
        }

        public string Remark
        {
            get { return _model.Remark; }
            set { _model.Remark = value; }
        }

        public bool IsTemplate
        {
            get { return _isTemplate; }
            private set { SetField(ref _isTemplate, value, "IsTemplate"); }
        }

        /// <summary>供 VM 侧更新模板标记。</summary>
        public void SetTemplate(bool isTemplate)
        {
            IsTemplate = isTemplate;
        }

        /// <summary>尺寸/大小文本（只读展示，UI 绑定需 Mode=OneWay）。</summary>
        public string SizeText
        {
            get
            {
                if (_model.FileSize >= 1024 * 1024)
                {
                    return (_model.FileSize / (1024.0 * 1024.0)).ToString("F1") + " MB";
                }
                if (_model.FileSize >= 1024)
                {
                    return (_model.FileSize / 1024.0).ToString("F1") + " KB";
                }
                return _model.FileSize + " B";
            }
        }

        public string MetaText
        {
            get
            {
                if (_model.Width > 0)
                {
                    return _model.Width + "×" + _model.Height + " / " + _model.Channels + "通道 / " + _model.PixelType;
                }
                return "元数据待读取";
            }
        }

        public string StatusText
        {
            get
            {
                switch (_model.FileStatus)
                {
                    case ImageFileStatus.Ok: return "正常";
                    case ImageFileStatus.Missing: return "缺失";
                    case ImageFileStatus.Damaged: return "损坏";
                    default: return "未知";
                }
            }
        }

        /// <summary>导入顺序文本（列表序号展示）。</summary>
        public string OrderText
        {
            get { return "#" + (_model.ImportOrder + 1); }
        }

        /// <summary>缩略图（懒加载；DecodePixelWidth 限制内存；失败返回 null 显示占位）。</summary>
        public BitmapSource Thumbnail
        {
            get
            {
                if (_thumbnail == null && !_thumbnailFailed)
                {
                    _thumbnail = TryLoadThumbnail();
                    if (_thumbnail == null)
                    {
                        _thumbnailFailed = true;
                    }
                }
                return _thumbnail;
            }
        }

        private BitmapSource TryLoadThumbnail()
        {
            try
            {
                if (!File.Exists(_model.SourcePath)) return null;
                var bitmap = new BitmapImage();
                bitmap.BeginInit();
                bitmap.CacheOption = BitmapCacheOption.OnLoad;
                bitmap.UriSource = new Uri(_model.SourcePath, UriKind.Absolute);
                bitmap.DecodePixelWidth = 96;
                bitmap.EndInit();
                bitmap.Freeze();
                return bitmap;
            }
            catch (Exception)
            {
                return null;
            }
        }

        /// <summary>元数据/状态更新后由 VM 调用（通知全部派生文本）。</summary>
        public void RefreshMetadata()
        {
            OnPropertyChanged("MetaText");
            OnPropertyChanged("StatusText");
            OnPropertyChanged("SizeText");
            OnPropertyChanged("CategoryId");
        }

        /// <summary>清空缓存缩略图（重定位路径后调用）。</summary>
        public void InvalidateThumbnail()
        {
            _thumbnail = null;
            _thumbnailFailed = false;
            OnPropertyChanged("Thumbnail");
        }
    }
}
```

---

### 文件 28: `ViewModels/OpenFileUiState.cs`

- **相对路径**: `ViewModels/OpenFileUiState.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `11.59 KB`
- **命名空间**: `Plugin.OpenFile.ViewModels`
- **核心类型**: `class OpenFileUiState`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.Data;
using Plugin.OpenFile.Model;

namespace Plugin.OpenFile.ViewModels
{
    /// <summary>
    /// UI 绑定状态对象（独立于 ModuleBase 派生 ViewModel，INPC 自管）。
    /// 只承载界面状态，不参与序列化；业务值持久化统一经 OpenFileSettings。
    /// </summary>
    public class OpenFileUiState : ObservableObject
    {
        #region 集合

        public ObservableCollection<ImageItemViewModel> Images { get; private set; }

        /// <summary>类别筛选结果（列表绑定源）。</summary>
        public ObservableCollection<ImageItemViewModel> FilteredImages { get; private set; }

        public ObservableCollection<DocumentItemViewModel> Documents { get; private set; }

        public ObservableCollection<ImageCategoryModel> Categories { get; private set; }

        #endregion

        #region 计数

        private int _imageCount;
        public int ImageCount
        {
            get { return _imageCount; }
            set { SetField(ref _imageCount, value, "ImageCount"); }
        }

        private int _filteredCount;
        public int FilteredCount
        {
            get { return _filteredCount; }
            set { SetField(ref _filteredCount, value, "FilteredCount"); }
        }

        private int _documentCount;
        public int DocumentCount
        {
            get { return _documentCount; }
            set { SetField(ref _documentCount, value, "DocumentCount"); }
        }

        #endregion

        #region 选中与标注

        private ImageItemViewModel _selectedImage;
        public ImageItemViewModel SelectedImage
        {
            get { return _selectedImage; }
            set { SetField(ref _selectedImage, value, "SelectedImage"); }
        }

        private DocumentItemViewModel _selectedDocument;
        public DocumentItemViewModel SelectedDocument
        {
            get { return _selectedDocument; }
            set { SetField(ref _selectedDocument, value, "SelectedDocument"); }
        }

        private ImageCategoryModel _assignCategory;
        public ImageCategoryModel AssignCategory
        {
            get { return _assignCategory; }
            set { SetField(ref _assignCategory, value, "AssignCategory"); }
        }

        private bool _selectedTemplateMarker;
        public bool SelectedTemplateMarker
        {
            get { return _selectedTemplateMarker; }
            set { SetField(ref _selectedTemplateMarker, value, "SelectedTemplateMarker"); }
        }

        private string _remarkText;
        public string RemarkText
        {
            get { return _remarkText; }
            set { SetField(ref _remarkText, value, "RemarkText"); }
        }

        #endregion

        #region 供图状态（修改经 VM 方法同步到 Settings）

        private ImageInputMode _supplyMode = ImageInputMode.CurrentImage;
        public ImageInputMode SupplyMode
        {
            get { return _supplyMode; }
            set { SetField(ref _supplyMode, value, "SupplyMode"); }
        }

        private bool _loopSequence;
        public bool LoopSequence
        {
            get { return _loopSequence; }
            set { SetField(ref _loopSequence, value, "LoopSequence"); }
        }

        #endregion

        #region 导出状态

        private string _exportTargetDirectory = string.Empty;
        public string ExportTargetDirectory
        {
            get { return _exportTargetDirectory; }
            set { SetField(ref _exportTargetDirectory, value, "ExportTargetDirectory"); }
        }

        private ExportScope _exportScope = ExportScope.All;
        public ExportScope ExportScope
        {
            get { return _exportScope; }
            set { SetField(ref _exportScope, value, "ExportScope"); }
        }

        private FolderOrganizationMode _exportFolderMode = FolderOrganizationMode.ByCategory;
        public FolderOrganizationMode ExportFolderMode
        {
            get { return _exportFolderMode; }
            set { SetField(ref _exportFolderMode, value, "ExportFolderMode"); }
        }

        private ExportConflictPolicy _exportConflict = ExportConflictPolicy.Skip;
        public ExportConflictPolicy ExportConflict
        {
            get { return _exportConflict; }
            set { SetField(ref _exportConflict, value, "ExportConflict"); }
        }

        private bool _exportIncludeUnlabeled = true;
        public bool ExportIncludeUnlabeled
        {
            get { return _exportIncludeUnlabeled; }
            set { SetField(ref _exportIncludeUnlabeled, value, "ExportIncludeUnlabeled"); }
        }

        private bool _exportIncludeTemplateCopy;
        public bool ExportIncludeTemplateCopy
        {
            get { return _exportIncludeTemplateCopy; }
            set { SetField(ref _exportIncludeTemplateCopy, value, "ExportIncludeTemplateCopy"); }
        }

        private bool _exportWriteManifest = true;
        public bool ExportWriteManifest
        {
            get { return _exportWriteManifest; }
            set { SetField(ref _exportWriteManifest, value, "ExportWriteManifest"); }
        }

        private bool _exportPreserveRelativePath;
        public bool ExportPreserveRelativePath
        {
            get { return _exportPreserveRelativePath; }
            set { SetField(ref _exportPreserveRelativePath, value, "ExportPreserveRelativePath"); }
        }

        private string _exportProgressText = string.Empty;
        public string ExportProgressText
        {
            get { return _exportProgressText; }
            set { SetField(ref _exportProgressText, value, "ExportProgressText"); }
        }

        private bool _isExporting;
        public bool IsExporting
        {
            get { return _isExporting; }
            set { SetField(ref _isExporting, value, "IsExporting"); }
        }

        #endregion

        #region 文档预览状态

        private DocumentPreviewMode _previewMode = DocumentPreviewMode.Original;
        public DocumentPreviewMode PreviewMode
        {
            get { return _previewMode; }
            set { SetField(ref _previewMode, value, "PreviewMode"); }
        }

        private string _originalText = string.Empty;
        public string OriginalText
        {
            get { return _originalText; }
            set { SetField(ref _originalText, value, "OriginalText"); }
        }

        private string _formattedText = string.Empty;
        public string FormattedText
        {
            get { return _formattedText; }
            set { SetField(ref _formattedText, value, "FormattedText"); }
        }

        private DataTable _previewTable;
        public DataTable PreviewTable
        {
            get { return _previewTable; }
            set { SetField(ref _previewTable, value, "PreviewTable"); }
        }

        private List<MarkdownBlock> _renderBlocks;
        public List<MarkdownBlock> RenderBlocks
        {
            get { return _renderBlocks; }
            set { SetField(ref _renderBlocks, value, "RenderBlocks"); }
        }

        private string _truncatedText = string.Empty;
        public string TruncatedText
        {
            get { return _truncatedText; }
            set { SetField(ref _truncatedText, value, "TruncatedText"); }
        }

        private string _previewErrorMessage = string.Empty;
        public string PreviewErrorMessage
        {
            get { return _previewErrorMessage; }
            set { SetField(ref _previewErrorMessage, value, "PreviewErrorMessage"); }
        }

        private bool _previewBusy;
        public bool PreviewBusy
        {
            get { return _previewBusy; }
            set { SetField(ref _previewBusy, value, "PreviewBusy"); }
        }

        private string _previewStatusText = string.Empty;
        public string PreviewStatusText
        {
            get { return _previewStatusText; }
            set { SetField(ref _previewStatusText, value, "PreviewStatusText"); }
        }

        private string _searchText = string.Empty;
        public string SearchText
        {
            get { return _searchText; }
            set { SetField(ref _searchText, value, "SearchText"); }
        }

        private string _matchCountText = string.Empty;
        public string MatchCountText
        {
            get { return _matchCountText; }
            set { SetField(ref _matchCountText, value, "MatchCountText"); }
        }

        private string _selectedEncodingName = "Auto";
        public string SelectedEncodingName
        {
            get { return _selectedEncodingName; }
            set { SetField(ref _selectedEncodingName, value, "SelectedEncodingName"); }
        }

        /// <summary>编码下拉选项（"Auto" = 自动识别）。</summary>
        public string[] EncodingOptions { get; private set; }

        /// <summary>供图模式选项。</summary>
        public ImageInputMode[] SupplyModes { get; private set; }

        /// <summary>预览模式选项。</summary>
        public DocumentPreviewMode[] PreviewModes { get; private set; }

        /// <summary>导出范围选项。</summary>
        public ExportScope[] ExportScopes { get; private set; }

        /// <summary>导出目录组织选项。</summary>
        public FolderOrganizationMode[] FolderModes { get; private set; }

        /// <summary>导出冲突策略选项。</summary>
        public ExportConflictPolicy[] ConflictPolicies { get; private set; }

        #endregion

        #region 全局状态

        private string _statusText = "就绪";
        public string StatusText
        {
            get { return _statusText; }
            set { SetField(ref _statusText, value, "StatusText"); }
        }

        #endregion

        public OpenFileUiState()
        {
            Images = new ObservableCollection<ImageItemViewModel>();
            FilteredImages = new ObservableCollection<ImageItemViewModel>();
            Documents = new ObservableCollection<DocumentItemViewModel>();
            Categories = new ObservableCollection<ImageCategoryModel>();
            EncodingOptions = new[] { "Auto", "UTF-8", "GB18030", "Unicode", "ASCII" };
            SupplyModes = (ImageInputMode[])Enum.GetValues(typeof(ImageInputMode));
            PreviewModes = (DocumentPreviewMode[])Enum.GetValues(typeof(DocumentPreviewMode));
            ExportScopes = (ExportScope[])Enum.GetValues(typeof(ExportScope));
            FolderModes = (FolderOrganizationMode[])Enum.GetValues(typeof(FolderOrganizationMode));
            ConflictPolicies = (ExportConflictPolicy[])Enum.GetValues(typeof(ExportConflictPolicy));
        }

        /// <summary>应用解析结果到预览区。</summary>
        public void ApplyPreview(FilePreviewModel model)
        {
            if (model == null)
            {
                ClearPreview();
                return;
            }
            OriginalText = model.OriginalText ?? string.Empty;
            FormattedText = model.FormattedText ?? string.Empty;
            PreviewTable = model.PreviewTable;
            RenderBlocks = model.RenderBlocks;
            TruncatedText = model.Truncated ? (model.TruncatedText ?? string.Empty) : string.Empty;
            PreviewErrorMessage = model.ErrorMessage ?? string.Empty;
        }

        /// <summary>清空预览区。</summary>
        public void ClearPreview()
        {
            OriginalText = string.Empty;
            FormattedText = string.Empty;
            PreviewTable = null;
            RenderBlocks = null;
            TruncatedText = string.Empty;
            PreviewErrorMessage = string.Empty;
            MatchCountText = string.Empty;
            PreviewStatusText = string.Empty;
        }
    }
}
```

---

### 文件 29: `ViewModels/OpenFileViewModel.cs`

- **相对路径**: `ViewModels/OpenFileViewModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `52.76 KB`
- **命名空间**: `Plugin.OpenFile.ViewModels`
- **核心类型**: `class OpenFileViewModel`, `class SamplePlan`, `class PreviewImageEventArgs`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: WPF/MVVM 视图模型相关代码

```csharp
﻿using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Collections.ObjectModel;
using System.IO;
using System.Linq;
using System.Runtime.Serialization;
using System.Threading;
using System.Threading.Tasks;
using System.Windows.Input;
using Plugin.OpenFile.Model;
using Plugin.OpenFile.Parsers;
using Plugin.OpenFile.Platform;
using Plugin.OpenFile.Services;
using VM.Halcon;
using VM.Halcon.Config;
using VM.Halcon.Model;
using VM.Start.Attributes;
using VM.Start.Common.Const;
using VM.Start.Common.Enums;
using VM.Start.Common.Provide;
using VM.Start.Core;

namespace Plugin.OpenFile.ViewModels
{
    /// <summary>
    /// Plugin.OpenFile ViewModel（文档导入插件）。
    /// 平台契约（台账 confirmed by source）：
    ///  - [Category]/[DisplayName]/[ModuleImageName]/[Serializable] 类特性 + 继承 ModuleBase；
    ///  - ExeModule()：Stopwatch.Restart() → 清空上周期 → 选样 → 校验 → 读图 → 发布输出 → ChangeModuleRunStatus；
    ///  - AddOutputParams()：base → 输出注册（经 VmOutputPublisher，语义类型 Image/String/Int/Bool/Double）；
    ///  - [OnDeserialized] 重建运行时字段（Plugin.Blob 模式）；
    ///  - 运行时字段全部 [NonSerialized]（HALCON 对象/任务/取消源不入序列化，文档 §6/§12）。
    /// </summary>
    [Category("常用工具")]
    [DisplayName("文件导入")]
    [ModuleImageName("OpenFile")]
    [Serializable]
    public class OpenFileViewModel : ModuleBase
    {
        #region 持久化配置

        /// <summary>插件配置与清单（二进制序列化持久化，文档 §12）。</summary>
        public OpenFileSettings Settings { get; set; }

        #endregion

        #region 运行时字段（[NonSerialized]）

        [NonSerialized] private object _syncRoot;
        [NonSerialized] private VmOutputPublisher _publisher;
        [NonSerialized] private VmImagePlatformAdapter _adapter;
        [NonSerialized] private System.Diagnostics.Stopwatch _execTimer;
        [NonSerialized] private SynchronizationContext _syncContext;

        [NonSerialized] private OpenFileUiState _ui;
        [NonSerialized] private RelayCommand _addImagesCommand;
        [NonSerialized] private RelayCommand _addImageFolderCommand;
        [NonSerialized] private RelayCommand _removeImageCommand;
        [NonSerialized] private RelayCommand _clearImagesCommand;
        [NonSerialized] private RelayCommand _setTemplateCommand;
        [NonSerialized] private RelayCommand _clearTemplateCommand;
        [NonSerialized] private RelayCommand _assignCategoryCommand;
        [NonSerialized] private RelayCommand _batchAssignCategoryCommand;
        [NonSerialized] private RelayCommand _exportSamplesCommand;
        [NonSerialized] private RelayCommand _cancelExportCommand;
        [NonSerialized] private RelayCommand _openDocumentCommand;
        [NonSerialized] private RelayCommand _removeDocumentCommand;
        [NonSerialized] private RelayCommand _clearDocumentsCommand;
        [NonSerialized] private RelayCommand _reloadPreviewCommand;
        [NonSerialized] private RelayCommand _convertCsvToMarkdownCommand;
        [NonSerialized] private RelayCommand _searchCommand;
        [NonSerialized] private RelayCommand _executeCommand;
        [NonSerialized] private RelayCommand _stopCommand;

        // 供图 / 模板 / 预览图像（插件创建并拥有，文档 §8 HALCON 所有权）
        [NonSerialized] private RImage _suppliedImage;
        [NonSerialized] private RImage _templateImage;
        [NonSerialized] private RImage _previewImage;

        [NonSerialized] private int _sequenceCursor;
        [NonSerialized] private int _previewRequestId;
        [NonSerialized] private CancellationTokenSource _exportCts;

        // 输出快照字段（仅执行线程写，AddOutputParams 读）
        [NonSerialized] private RImage _outImage;
        [NonSerialized] private string _outImagePath;
        [NonSerialized] private string _outSampleId;
        [NonSerialized] private string _outCategory;
        [NonSerialized] private int _outWidth;
        [NonSerialized] private int _outHeight;
        [NonSerialized] private int _outChannels;
        [NonSerialized] private string _outPixelType;
        [NonSerialized] private bool _outIsSequenceEnd;
        [NonSerialized] private bool _outIsValid;
        [NonSerialized] private string _outStatusCode;
        [NonSerialized] private string _outStatusText;
        [NonSerialized] private string _outTemplatePath;
        [NonSerialized] private double _outElapsedMs;

        #endregion

        #region 构造与序列化重建

        public OpenFileViewModel()
        {
            Settings = new OpenFileSettings();
            InitRuntime();
        }

        [OnDeserialized]
        private void OnDeserialized(StreamingContext context)
        {
            if (Settings == null)
            {
                Settings = new OpenFileSettings();
            }
            Settings.MigrateDefaults();
            InitRuntime();
        }

        /// <summary>重建运行时对象（构造 / 反序列化共用；Plugin.Blob InitRuntime 模式）。</summary>
        private void InitRuntime()
        {
            _syncRoot = new object();
            _publisher = new VmOutputPublisher();
            _adapter = new VmImagePlatformAdapter();
            _execTimer = new System.Diagnostics.Stopwatch();
            _syncContext = SynchronizationContext.Current ?? new SynchronizationContext();

            if (_ui == null)
            {
                _ui = new OpenFileUiState();
            }
            _ui.Images.Clear();
            _ui.Documents.Clear();
            _ui.Categories.Clear();

            lock (_syncRoot)
            {
                foreach (var category in Settings.Categories)
                {
                    _ui.Categories.Add(category);
                }
                foreach (var img in Settings.ImageItems)
                {
                    var vm = new ImageItemViewModel(img);
                    vm.SetTemplate(string.Equals(img.Id, Settings.TemplateImageId));
                    _ui.Images.Add(vm);
                }
                foreach (var doc in Settings.DocumentItems)
                {
                    _ui.Documents.Add(new DocumentItemViewModel(doc));
                }
                _ui.ImageCount = Settings.ImageItems.Count;
                _ui.DocumentCount = Settings.DocumentItems.Count;
                ApplyCategoryFilterLocked();
            }
            SyncUiFromSettings();

            // UI 状态变更 → Settings 实时同步（供图模式/循环/编码是执行关键配置）
            _ui.PropertyChanged += OnUiPropertyChanged;
        }

        /// <summary>恢复（反序列化/构造）后把 Settings 值刷进 UI 状态。</summary>
        private void SyncUiFromSettings()
        {
            _ui.SupplyMode = Settings.ImageInputMode;
            _ui.LoopSequence = Settings.LoopSequence;
            _ui.SelectedEncodingName = Settings.DocumentEncoding;
            _ui.ExportTargetDirectory = Settings.Export.TargetDirectory;
            _ui.ExportScope = Settings.Export.Scope;
            _ui.ExportFolderMode = Settings.Export.FolderMode;
            _ui.ExportConflict = Settings.Export.ConflictPolicy;
            _ui.ExportIncludeUnlabeled = Settings.Export.IncludeUnlabeled;
            _ui.ExportIncludeTemplateCopy = Settings.Export.IncludeTemplateCopy;
            _ui.ExportWriteManifest = Settings.Export.WriteManifest;
            _ui.ExportPreserveRelativePath = Settings.Export.PreserveRelativePath;
            _ui.AssignCategory = _ui.Categories.Count > 0 ? _ui.Categories[0] : null;
        }

        /// <summary>把执行关键 UI 状态同步回 Settings（项目保存时随之序列化）。</summary>
        private void OnUiPropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
        {
            switch (e.PropertyName)
            {
                case "SupplyMode":
                    Settings.ImageInputMode = _ui.SupplyMode;
                    break;
                case "LoopSequence":
                    Settings.LoopSequence = _ui.LoopSequence;
                    break;
                case "SelectedEncodingName":
                    Settings.DocumentEncoding = _ui.SelectedEncodingName;
                    break;
                case "ExportTargetDirectory":
                    Settings.Export.TargetDirectory = _ui.ExportTargetDirectory;
                    break;
            }
        }

        /// <summary>当前类别筛选值（View 加载时恢复 ComboBox 用）。</summary>
        public string CurrentFilterCategoryId
        {
            get { return Settings.SelectedCategoryId; }
        }

        /// <summary>切换选中文档（View SelectionChanged 调用；触发预览请求）。</summary>
        public void SelectDocument(DocumentItemViewModel item)
        {
            Ui.SelectedDocument = item;
            if (item == null)
            {
                Ui.ClearPreview();
                return;
            }
            item.Model.EncodingName = Settings.DocumentEncoding;
            RequestPreview(false);
        }

        /// <summary>应用类别筛选（View 筛选 ComboBox 调用；空/全部传 null）。</summary>
        public void ApplyCategoryFilter(string categoryId)
        {
            lock (_syncRoot)
            {
                Settings.SelectedCategoryId = categoryId ?? string.Empty;
                ApplyCategoryFilterLocked();
            }
        }

        /// <summary>切换文档编码（View 编码 ComboBox 调用）。</summary>
        public void SetDocumentEncoding(string encodingName)
        {
            Settings.DocumentEncoding = encodingName ?? "Auto";
            _ui.SelectedEncodingName = Settings.DocumentEncoding;
            var selected = Ui.SelectedDocument;
            if (selected != null)
            {
                selected.Model.EncodingName = Settings.DocumentEncoding;
                RequestPreview(true);
            }
        }

        #endregion

        #region UI 状态与命令暴露

        /// <summary>UI 绑定状态（不序列化；显式后备字段模式，自动属性无法标记 NonSerialized）。</summary>
        public OpenFileUiState Ui
        {
            get { return _ui; }
        }

        public ICommand AddImagesCommand
        {
            get { return _addImagesCommand ?? (_addImagesCommand = new RelayCommand(_ => AddImageFiles())); }
        }

        public ICommand AddImageFolderCommand
        {
            get { return _addImageFolderCommand ?? (_addImageFolderCommand = new RelayCommand(_ => AddImageFolder())); }
        }

        public ICommand RemoveImageCommand
        {
            get { return _removeImageCommand ?? (_removeImageCommand = new RelayCommand(_ => RemoveSelectedImage())); }
        }

        public ICommand ClearImagesCommand
        {
            get { return _clearImagesCommand ?? (_clearImagesCommand = new RelayCommand(_ => ClearImages())); }
        }

        public ICommand SetTemplateCommand
        {
            get { return _setTemplateCommand ?? (_setTemplateCommand = new RelayCommand(_ => SetTemplate())); }
        }

        public ICommand ClearTemplateCommand
        {
            get { return _clearTemplateCommand ?? (_clearTemplateCommand = new RelayCommand(_ => ClearTemplate())); }
        }

        public ICommand AssignCategoryCommand
        {
            get { return _assignCategoryCommand ?? (_assignCategoryCommand = new RelayCommand(_ => AssignCategoryToSelected())); }
        }

        public ICommand BatchAssignCategoryCommand
        {
            get
            {
                return _batchAssignCategoryCommand ?? (_batchAssignCategoryCommand =
                    new RelayCommand(param => BatchAssignCategory(param as System.Collections.IList)));
            }
        }

        public ICommand ExportSamplesCommand
        {
            get { return _exportSamplesCommand ?? (_exportSamplesCommand = new RelayCommand(_ => ExportSamples(), _ => !_ui.IsExporting)); }
        }

        public ICommand CancelExportCommand
        {
            get { return _cancelExportCommand ?? (_cancelExportCommand = new RelayCommand(_ => CancelExport(), _ => _ui.IsExporting)); }
        }

        public ICommand StopCommand
        {
            get { return _stopCommand ?? (_stopCommand = new RelayCommand(_ => CancelExport(), _ => _ui.IsExporting)); }
        }

        public ICommand OpenDocumentCommand
        {
            get { return _openDocumentCommand ?? (_openDocumentCommand = new RelayCommand(_ => AddDocuments())); }
        }

        public ICommand RemoveDocumentCommand
        {
            get { return _removeDocumentCommand ?? (_removeDocumentCommand = new RelayCommand(_ => RemoveSelectedDocument())); }
        }

        public ICommand ClearDocumentsCommand
        {
            get { return _clearDocumentsCommand ?? (_clearDocumentsCommand = new RelayCommand(_ => ClearDocuments())); }
        }

        public ICommand ReloadPreviewCommand
        {
            get { return _reloadPreviewCommand ?? (_reloadPreviewCommand = new RelayCommand(_ => RequestPreview(true))); }
        }

        public ICommand ConvertCsvToMarkdownCommand
        {
            get { return _convertCsvToMarkdownCommand ?? (_convertCsvToMarkdownCommand = new RelayCommand(_ => ConvertCsvToMarkdown())); }
        }

        public ICommand SearchCommand
        {
            get { return _searchCommand ?? (_searchCommand = new RelayCommand(_ => SearchPreviewText())); }
        }

        /// <summary>手工执行：复用 ExeModule() 路径，不另写第二套执行逻辑（手册 Phase5 红线）。</summary>
        public ICommand ExecuteCommand
        {
            get { return _executeCommand ?? (_executeCommand = new RelayCommand(_ => ExeModule())); }
        }

        #endregion

        #region 图像导入

        private void AddImageFiles()
        {
            var dialog = new Microsoft.Win32.OpenFileDialog
            {
                Title = "选择图像文件",
                Filter = "图像文件|*.png;*.jpg;*.jpeg;*.bmp;*.tif;*.tiff|全部文件|*.*",
                Multiselect = true
            };
            if (dialog.ShowDialog() != true)
            {
                return;
            }
            ImportIntoCatalog(ImageImportService.ImportFiles(dialog.FileNames, NextImportOrder(), ExistingPaths()));
        }

        private void AddImageFolder()
        {
            using (var dialog = new System.Windows.Forms.FolderBrowserDialog
            {
                Description = "选择图像文件夹",
                ShowNewFolderButton = false
            })
            {
                if (dialog.ShowDialog() != System.Windows.Forms.DialogResult.OK)
                {
                    return;
                }
                string exportDir = Settings.Export != null ? Settings.Export.TargetDirectory : string.Empty;
                var exclude = string.IsNullOrEmpty(exportDir) ? null : new[] { exportDir };
                var imported = ImageImportService.ImportFolder(dialog.SelectedPath, Settings.RecursiveFolderScan,
                    NextImportOrder(), ExistingPaths(), exclude);
                ImportIntoCatalog(imported);
            }
        }

        private void ImportIntoCatalog(List<ImageItemModel> imported)
        {
            if (imported == null || imported.Count == 0)
            {
                Ui.StatusText = "没有新图像可导入（重复或不支持的文件已过滤）";
                return;
            }
            lock (_syncRoot)
            {
                foreach (var item in imported)
                {
                    Settings.ImageItems.Add(item);
                    _ui.Images.Add(new ImageItemViewModel(item));
                }
                _ui.ImageCount = Settings.ImageItems.Count;
                ApplyCategoryFilterLocked();
            }
            Ui.StatusText = "已导入 " + imported.Count + " 张图像";
        }

        private int NextImportOrder()
        {
            lock (_syncRoot)
            {
                return Settings.ImageItems.Count;
            }
        }

        private List<string> ExistingPaths()
        {
            lock (_syncRoot)
            {
                return Settings.ImageItems.Select(i => i.SourcePath).ToList();
            }
        }

        private void RemoveSelectedImage()
        {
            var selected = Ui.SelectedImage;
            if (selected == null) return;
            Interlocked.Increment(ref _previewRequestId);
            lock (_syncRoot)
            {
                var model = Settings.ImageItems.FirstOrDefault(i => string.Equals(i.Id, selected.Id));
                if (model != null) Settings.ImageItems.Remove(model);
                _ui.Images.Remove(selected);
                _ui.ImageCount = Settings.ImageItems.Count;
                if (string.Equals(Settings.SelectedImageId, selected.Id)) Settings.SelectedImageId = string.Empty;
                if (string.Equals(Settings.TemplateImageId, selected.Id))
                {
                    Settings.TemplateImageId = string.Empty;
                    InvalidateTemplateCache();
                }
                ApplyCategoryFilterLocked();
            }
            Ui.SelectedImage = null;
            ClearPreviewImage();
            Ui.StatusText = "已移除 " + selected.DisplayName;
        }

        private void ClearImages()
        {
            Interlocked.Increment(ref _previewRequestId);
            lock (_syncRoot)
            {
                Settings.ImageItems.Clear();
                _ui.Images.Clear();
                _ui.ImageCount = 0;
                Settings.SelectedImageId = string.Empty;
                Settings.TemplateImageId = string.Empty;
                InvalidateTemplateCache();
                ApplyCategoryFilterLocked();
            }
            Ui.SelectedImage = null;
            Ui.SelectedTemplateMarker = false;
            ClearPreviewImage();
            Ui.StatusText = "已清空图像清单（源文件未删除）";
        }

        #endregion

        #region 模板与分类

        private void SetTemplate()
        {
            var selected = Ui.SelectedImage;
            if (selected == null)
            {
                Ui.StatusText = "请先选择要设为模板的图像";
                return;
            }
            // 单实例唯一模板（文档阶段4）：取消旧模板标记
            lock (_syncRoot)
            {
                foreach (var img in _ui.Images)
                {
                    img.SetTemplate(false);
                }
                Settings.TemplateImageId = selected.Id;
                selected.SetTemplate(true);
                InvalidateTemplateCache();
            }
            Ui.SelectedTemplateMarker = true;
            Ui.StatusText = "已设为模板：" + selected.DisplayName + "（不会自动训练，仅标记与发布）";
        }

        private void ClearTemplate()
        {
            lock (_syncRoot)
            {
                foreach (var img in _ui.Images)
                {
                    img.SetTemplate(false);
                }
                Settings.TemplateImageId = string.Empty;
                InvalidateTemplateCache();
            }
            Ui.SelectedTemplateMarker = false;
            Ui.StatusText = "已取消模板";
        }

        private void AssignCategoryToSelected()
        {
            var selected = Ui.SelectedImage;
            var category = Ui.AssignCategory;
            if (selected == null || category == null)
            {
                Ui.StatusText = "请先选择图像与目标类别";
                return;
            }
            selected.Model.CategoryId = category.Id;
            selected.RefreshMetadata();
            lock (_syncRoot)
            {
                ApplyCategoryFilterLocked();
            }
            Ui.StatusText = "已标注：" + selected.DisplayName + " → " + category.Name;
        }

        /// <summary>批量分类：parameter 为 View 传入的多选集合（或按当前筛选结果）。</summary>
        private void BatchAssignCategory(System.Collections.IList selectedItems)
        {
            var category = Ui.AssignCategory;
            if (category == null)
            {
                Ui.StatusText = "请先选择目标类别";
                return;
            }
            List<ImageItemViewModel> targets = new List<ImageItemViewModel>();
            if (selectedItems != null && selectedItems.Count > 0)
            {
                foreach (var obj in selectedItems)
                {
                    var vm = obj as ImageItemViewModel;
                    if (vm != null) targets.Add(vm);
                }
            }
            if (targets.Count == 0)
            {
                // 无多选时按当前筛选结果批量（文档阶段4：批量标注）
                targets = _ui.Images.ToList();
            }
            foreach (var vm in targets)
            {
                vm.Model.CategoryId = category.Id;
                vm.RefreshMetadata();
            }
            lock (_syncRoot)
            {
                ApplyCategoryFilterLocked();
            }
            Ui.StatusText = "批量标注完成：" + targets.Count + " 张 → " + category.Name;
        }

        private void InvalidateTemplateCache()
        {
            if (_templateImage != null)
            {
                _adapter.ReleaseImage(_templateImage);
                _templateImage = null;
            }
        }

        private void ApplyCategoryFilterLocked()
        {
            string filter = Settings.SelectedCategoryId;
            var list = string.IsNullOrEmpty(filter)
                ? _ui.Images.ToList()
                : _ui.Images.Where(i => string.Equals(i.Model.CategoryId, filter)).ToList();
            _ui.FilteredImages.Clear();
            foreach (var item in list)
            {
                _ui.FilteredImages.Add(item);
            }
            _ui.FilteredCount = _ui.FilteredImages.Count;
        }

        #endregion

        #region 样本导出

        private void SyncExportFromUi()
        {
            if (Settings.Export == null)
            {
                Settings.Export = new ExportSettings();
            }

            Settings.Export.TargetDirectory = _ui.ExportTargetDirectory ?? string.Empty;
            Settings.Export.Scope = _ui.ExportScope;
            Settings.Export.FolderMode = _ui.ExportFolderMode;
            Settings.Export.ConflictPolicy = _ui.ExportConflict;
            Settings.Export.IncludeUnlabeled = _ui.ExportIncludeUnlabeled;
            Settings.Export.IncludeTemplateCopy = _ui.ExportIncludeTemplateCopy;
            Settings.Export.WriteManifest = _ui.ExportWriteManifest;
            Settings.Export.PreserveRelativePath = _ui.ExportPreserveRelativePath;
        }

        private void ExportSamples()
        {
            if (_ui.IsExporting)
            {
                return;
            }
            SyncExportFromUi();
            var settings = Settings.Export;
            if (settings == null || string.IsNullOrWhiteSpace(settings.TargetDirectory))
            {
                Ui.StatusText = "请先设置导出目标目录";
                return;
            }

            List<ImageItemModel> snapshot;
            ImageItemModel templateItem;
            Dictionary<string, string> categoryNames;
            lock (_syncRoot)
            {
                IEnumerable<ImageItemViewModel> scope = _ui.Images;
                if (settings.Scope == ExportScope.Filtered)
                {
                    scope = _ui.FilteredImages;
                }
                else if (settings.Scope == ExportScope.Selected && Ui.SelectedImage != null)
                {
                    scope = new[] { Ui.SelectedImage };
                }
                snapshot = scope.Select(vm => vm.Model).ToList();
                templateItem = Settings.ImageItems.FirstOrDefault(i => string.Equals(i.Id, Settings.TemplateImageId));
                categoryNames = Settings.Categories.ToDictionary(c => c.Id, c => c.Name);
            }

            if (snapshot.Count == 0 && templateItem == null)
            {
                Ui.StatusText = "导出范围内没有样本";
                return;
            }

            _exportCts = new CancellationTokenSource();
            Ui.IsExporting = true;
            Ui.ExportProgressText = "导出中… 0/" + snapshot.Count;
            var token = _exportCts.Token;
            var progress = new Progress<int>(done =>
            {
                Ui.ExportProgressText = "导出中… " + done + "/" + snapshot.Count;
            });

            Task.Run(() => SampleExportService.Export(snapshot, templateItem, categoryNames, settings, token, progress), token)
                .ContinueWith(t =>
                {
                    Ui.IsExporting = false;
                    if (t.IsCanceled)
                    {
                        Ui.ExportProgressText = "导出已取消";
                        Ui.StatusText = "导出已取消";
                        return;
                    }
                    if (t.IsFaulted)
                    {
                        Ui.ExportProgressText = "导出失败：" + (t.Exception != null ? t.Exception.GetBaseException().Message : "未知错误");
                        Ui.StatusText = Ui.ExportProgressText;
                        if (t.Exception != null)
                        {
                            Logger.GetExceptionMsg(t.Exception.GetBaseException());
                        }
                        return;
                    }
                    var result = t.Result;
                    Ui.ExportProgressText = result.SummaryText;
                    Ui.StatusText = result.SummaryText;
                });
        }

        private void CancelExport()
        {
            if (_exportCts != null)
            {
                try
                {
                    _exportCts.Cancel();
                }
                catch (ObjectDisposedException)
                {
                    // 导出已结束
                }
                Ui.StatusText = "正在取消导出…";
            }
        }

        #endregion

        #region 文档导入与预览

        /// <summary>拖拽导入入口（View 调用）：文件夹导入图像，文件按类型分流（文档 §11.1）。</summary>
        public void AddDroppedFiles(System.Collections.IEnumerable paths)
        {
            if (paths == null) return;
            var images = new List<string>();
            var folders = new List<string>();
            var docs = new List<string>();
            foreach (var obj in paths)
            {
                string path = obj as string;
                if (string.IsNullOrWhiteSpace(path)) continue;
                if (Directory.Exists(path))
                {
                    folders.Add(path);
                    continue;
                }
                if (!File.Exists(path)) continue;
                var kind = FileRecognitionService.RecognizeKind(path);
                if (kind == FileKind.Image)
                {
                    images.Add(path);
                }
                else if (kind != FileKind.Unsupported && kind != FileKind.Unknown)
                {
                    docs.Add(path);
                }
            }
            if (folders.Count > 0)
            {
                foreach (var folder in folders)
                {
                    string exportDir = Settings.Export != null ? Settings.Export.TargetDirectory : string.Empty;
                    var exclude = string.IsNullOrEmpty(exportDir) ? null : new[] { exportDir };
                    var imported = ImageImportService.ImportFolder(folder, Settings.RecursiveFolderScan,
                        NextImportOrder(), ExistingPaths(), exclude);
                    ImportIntoCatalog(imported);
                }
            }
            if (images.Count > 0)
            {
                ImportIntoCatalog(ImageImportService.ImportFiles(images, NextImportOrder(), ExistingPaths()));
            }
            if (docs.Count > 0)
            {
                AddDocumentPaths(docs);
            }
        }

        private void AddDocuments()
        {
            var dialog = new Microsoft.Win32.OpenFileDialog
            {
                Title = "选择文档文件",
                Filter = "全部支持|*.md;*.markdown;*.txt;*.log;*.csv;*.tsv;*.json;*.hdev;*.hdvp|Markdown|*.md;*.markdown|文本|*.txt;*.log|表格|*.csv;*.tsv|JSON|*.json|HALCON 脚本|*.hdev;*.hdvp|全部文件|*.*",
                Multiselect = true
            };
            if (dialog.ShowDialog() != true)
            {
                return;
            }
            AddDocumentPaths(dialog.FileNames);
        }

        /// <summary>按路径批量添加文档（对话框与拖拽共用）。</summary>
        private void AddDocumentPaths(System.Collections.IEnumerable paths)
        {
            int added = 0;
            lock (_syncRoot)
            {
                foreach (var obj in paths)
                {
                    string path = obj as string;
                    if (string.IsNullOrWhiteSpace(path)) continue;
                    string full = Path.GetFullPath(path);
                    if (Settings.DocumentItems.Any(d => string.Equals(d.SourcePath, full, StringComparison.OrdinalIgnoreCase)))
                    {
                        continue;
                    }
                    var recognition = FileRecognitionService.Recognize(full);
                    if (recognition.Kind == FileKind.Unsupported || recognition.Kind == FileKind.Unknown)
                    {
                        continue;
                    }
                    var model = new DocumentItemModel
                    {
                        SourcePath = full,
                        DisplayName = Path.GetFileName(full),
                        Extension = recognition.Extension,
                        FileSize = recognition.FileSize,
                        DocumentType = recognition.Kind,
                        EncodingName = Settings.DocumentEncoding
                    };
                    Settings.DocumentItems.Add(model);
                    _ui.Documents.Add(new DocumentItemViewModel(model));
                    added++;
                }
                _ui.DocumentCount = Settings.DocumentItems.Count;
            }
            Ui.StatusText = "已添加 " + added + " 个文档";
        }

        private void RemoveSelectedDocument()
        {
            var selected = Ui.SelectedDocument;
            if (selected == null) return;
            lock (_syncRoot)
            {
                var model = Settings.DocumentItems.FirstOrDefault(d => string.Equals(d.Id, selected.Id));
                if (model != null) Settings.DocumentItems.Remove(model);
                _ui.Documents.Remove(selected);
                _ui.DocumentCount = Settings.DocumentItems.Count;
            }
            Ui.SelectedDocument = null;
            Ui.StatusText = "已移除 " + selected.DisplayName;
        }

        private void ClearDocuments()
        {
            lock (_syncRoot)
            {
                Settings.DocumentItems.Clear();
                _ui.Documents.Clear();
                _ui.DocumentCount = 0;
            }
            Ui.SelectedDocument = null;
            Ui.ClearPreview();
            Ui.StatusText = "已清空文档清单（源文件未修改）";
        }

        /// <summary>请求预览（选中变化 / 手动刷新；请求 ID 防旧结果覆盖，文档 §17 风险表）。</summary>
        private void RequestPreview(bool forceReload)
        {
            var selected = Ui.SelectedDocument;
            if (selected == null)
            {
                Ui.ClearPreview();
                return;
            }

            int requestId = Interlocked.Increment(ref _previewRequestId);
            Ui.PreviewBusy = true;
            Ui.PreviewStatusText = "解析中…";

            string path = selected.Model.SourcePath;
            FileKind kind = selected.Model.DocumentType;
            string encodingName = selected.Model.EncodingName;
            string delimiter = Settings.CsvDelimiter;
            bool hasHeader = Settings.CsvHasHeader;
            int maxBytes = Settings.PreviewMaxBytes;
            int maxLines = Settings.PreviewMaxLines;

            Task.Factory.StartNew(() =>
            {
                return DocumentPreviewService.Preview(path, kind, encodingName, delimiter, hasHeader, maxBytes, maxLines, CancellationToken.None);
            }).ContinueWith(t =>
            {
                if (t.IsFaulted)
                {
                    if (t.Exception != null)
                    {
                        Logger.GetExceptionMsg(t.Exception.GetBaseException());
                    }
                }
                PostToUi(() =>
                {
                    if (requestId != Volatile.Read(ref _previewRequestId))
                    {
                        return; // 旧请求，丢弃（不回写，文档阶段6验收）
                    }
                    Ui.PreviewBusy = false;
                    if (t.IsFaulted)
                    {
                        Ui.PreviewStatusText = "预览失败：" + (t.Exception != null ? t.Exception.GetBaseException().Message : "未知错误");
                        return;
                    }
                    var model = t.Result;
                    Ui.ApplyPreview(model);
                    selected.Model.ParseStatus = model.ErrorMessage.Length > 0
                        ? DocumentParseStatus.Failed
                        : (model.Truncated ? DocumentParseStatus.Truncated : DocumentParseStatus.Ok);
                    selected.Model.LastError = model.ErrorMessage;
                    selected.RefreshStatus();
                    Ui.PreviewStatusText = model.ErrorMessage.Length > 0
                        ? model.ErrorMessage
                        : (model.Truncated ? model.TruncatedText : "解析完成");
                });
            });
        }

        private void ConvertCsvToMarkdown()
        {
            var table = Ui.PreviewTable;
            if (table == null)
            {
                Ui.StatusText = "当前文档没有表格数据（请先解析 CSV/TSV）";
                return;
            }
            Ui.FormattedText = MarkdownParser.DataTableToMarkdown(table, Settings.CsvHasHeader);
            Ui.PreviewMode = DocumentPreviewMode.Formatted;
            Ui.StatusText = "已转换为 Markdown 表格";
        }

        /// <summary>文本搜索：统计匹配次数（定位滚动由编辑器原生存找完成）。</summary>
        private void SearchPreviewText()
        {
            string keyword = Ui.SearchText;
            if (string.IsNullOrEmpty(keyword))
            {
                Ui.MatchCountText = string.Empty;
                return;
            }
            string source = Ui.OriginalText ?? string.Empty;
            int count = 0, index = 0;
            while ((index = source.IndexOf(keyword, index, StringComparison.OrdinalIgnoreCase)) >= 0)
            {
                count++;
                index += keyword.Length;
            }
            Ui.MatchCountText = "匹配 " + count + " 处";
        }

        #endregion

        #region 编辑器预览（与工作流输出隔离）

        /// <summary>预览图像就绪事件（View 订阅后赋给 VMHWindowControl；UI 线程发出）。</summary>
        [field: NonSerialized]
        public event EventHandler<PreviewImageEventArgs> PreviewImageChanged;

        /// <summary>切换选中图像（列表联动调用）：异步读图更新编辑器预览 + 填充元数据。</summary>
        public void SelectImage(ImageItemViewModel item)
        {
            Ui.SelectedImage = item;
            if (item == null)
            {
                Settings.SelectedImageId = string.Empty;
                ClearPreviewImage();
                return;
            }
            Settings.SelectedImageId = item.Id;
            Ui.SelectedTemplateMarker = string.Equals(item.Id, Settings.TemplateImageId);
            Ui.RemarkText = item.Model.Remark ?? string.Empty;
            RequestPreviewImage(item);
        }

        /// <summary>备注写回（UI 失焦调用，可序列化到清单）。</summary>
        public void CommitRemark()
        {
            var item = Ui.SelectedImage;
            if (item == null) return;
            item.Model.Remark = Ui.RemarkText ?? string.Empty;
        }

        /// <summary>导出目标目录浏览（View 调用；返回是否有效选择）。</summary>
        public bool BrowseExportDirectory()
        {
            using (var dialog = new System.Windows.Forms.FolderBrowserDialog { Description = "选择样本导出目录" })
            {
                if (dialog.ShowDialog() != System.Windows.Forms.DialogResult.OK)
                {
                    return false;
                }
                Settings.Export.TargetDirectory = dialog.SelectedPath;
                Ui.ExportTargetDirectory = dialog.SelectedPath;
                return true;
            }
        }

        private void RequestPreviewImage(ImageItemViewModel item)
        {
            int requestId = Interlocked.Increment(ref _previewRequestId);
            string path = item.Model.SourcePath;

            Task.Factory.StartNew(() =>
            {
                var probe = _adapter.GetMetadata(path);
                RImage image = probe.Success ? _adapter.LoadImage(path) : null;
                return new { RequestId = requestId, Item = item, Probe = probe, Image = image };
            }).ContinueWith(t =>
            {
                if (t.IsCanceled || t.IsFaulted)
                {
                    if (t.IsFaulted)
                    {
                        PostToUi(() => { Ui.PreviewStatusText = "预览失败：" + (t.Exception != null ? t.Exception.GetBaseException().Message : ""); });
                        if (t.Exception != null) Logger.GetExceptionMsg(t.Exception.GetBaseException());
                    }
                    return;
                }
                var payload = t.Result;
                if (payload.RequestId != Volatile.Read(ref _previewRequestId))
                {
                    _adapter.ReleaseImage(payload.Image); // 旧请求图像直接释放
                    return;
                }
                PostToUi(() =>
                {
                    // 元数据回填（导入时延迟读取，文档 §8）
                    if (payload.Probe.Success)
                    {
                        payload.Item.Model.Width = payload.Probe.Width;
                        payload.Item.Model.Height = payload.Probe.Height;
                        payload.Item.Model.Channels = payload.Probe.Channels;
                        payload.Item.Model.PixelType = payload.Probe.PixelType;
                        payload.Item.Model.FileStatus = ImageFileStatus.Ok;
                        payload.Item.Model.LastError = string.Empty;
                    }
                    else
                    {
                        payload.Item.Model.FileStatus = ImageFileStatus.Damaged;
                        payload.Item.Model.LastError = payload.Probe.Error;
                    }
                    payload.Item.RefreshMetadata();

                    // 替换预览图像：先发新图（View 同步赋值窗口），再释放旧图
                    var old = _previewImage;
                    _previewImage = payload.Image;
                    Ui.PreviewStatusText = payload.Probe.Success
                        ? payload.Probe.Width + "×" + payload.Probe.Height + " / " + payload.Probe.Channels + " 通道 / " + payload.Probe.PixelType
                        : "图像读取失败：" + payload.Probe.Error;
                    var handler = PreviewImageChanged;
                    if (handler != null)
                    {
                        handler(this, new PreviewImageEventArgs(payload.Image));
                    }
                    if (old != null)
                    {
                        _adapter.ReleaseImage(old);
                    }
                });
            });
        }

        private void ClearPreviewImage()
        {
            var old = _previewImage;
            _previewImage = null;
            var handler = PreviewImageChanged;
            if (handler != null)
            {
                handler(this, new PreviewImageEventArgs(null));
            }
            if (old != null)
            {
                _adapter.ReleaseImage(old);
            }
        }

        private void PostToUi(Action action)
        {
            var ctx = _syncContext;
            if (ctx != null)
            {
                ctx.Post(_ => action(), null);
            }
            else
            {
                action();
            }
        }

        #endregion

        #region 执行（供图）

        /// <summary>
        /// 流程执行入口：按供图模式发布当前/顺序/循环图像。
        /// 顺序：重启计时 → 清上周期 → 选样 → 校验 → 读图 → 发布 → 推进游标 → 状态（手册 §5.2）。
        /// </summary>
        public override bool ExeModule()
        {
            Stopwatch.Restart();
            if (_execTimer == null)
            {
                _execTimer = System.Diagnostics.Stopwatch.StartNew();
            }
            _execTimer.Restart();

            // 1. 清除上一周期结果（失败周期不得暴露旧图像，文档 §13.2）
            ReleaseSuppliedImage();
            ClearCycleOutputs();

            RImage frame = null;
            try
            {
                // 2. 选样（模式 + 游标 + 类别；稳定 ID 而非列表索引，文档 §7.3）
                SamplePlan plan = SelectSample();
                if (!plan.Ok)
                {
                    _outStatusCode = plan.StatusCode;
                    _outStatusText = plan.StatusText;
                    _outIsSequenceEnd = plan.IsSequenceEnd;
                    ChangeModuleRunStatus(eRunStatus.NG);
                    return false;
                }

                var model = plan.Item.Model;

                // 3. 文件存在校验（E02：缺失标记，不删除记录）
                if (!File.Exists(model.SourcePath))
                {
                    model.FileStatus = ImageFileStatus.Missing;
                    model.LastError = "文件不存在";
                    plan.Item.RefreshMetadata();
                    _outStatusCode = "FILE_MISSING";
                    _outStatusText = "文件不存在：" + model.SourcePath;
                    ChangeModuleRunStatus(eRunStatus.NG);
                    return false;
                }

                // 4. 读图（HALCON；损坏文件单独诊断，不影响批次，文档 E03）
                try
                {
                    frame = _adapter.LoadImage(model.SourcePath);
                }
                catch (Exception ex)
                {
                    model.FileStatus = ImageFileStatus.Damaged;
                    model.LastError = ex.Message;
                    plan.Item.RefreshMetadata();
                    _outStatusCode = "IMAGE_DAMAGED";
                    _outStatusText = "图像读取失败：" + ex.Message;
                    ChangeModuleRunStatus(eRunStatus.NG);
                    return false;
                }

                // 5. 元数据回填
                var probe = _adapter.GetMetadata(model.SourcePath);
                if (probe.Success)
                {
                    model.Width = probe.Width;
                    model.Height = probe.Height;
                    model.Channels = probe.Channels;
                    model.PixelType = probe.PixelType;
                }
                model.FileStatus = ImageFileStatus.Ok;
                model.LastError = string.Empty;
                plan.Item.RefreshMetadata();

                // 6. 发布输出（一次性，完整成功后）
                _suppliedImage = frame;
                frame = null; // 所有权移交输出字段
                _outImage = _suppliedImage;
                _outImagePath = model.SourcePath;
                _outSampleId = model.Id;
                _outCategory = plan.CategoryName;
                _outWidth = model.Width;
                _outHeight = model.Height;
                _outChannels = model.Channels;
                _outPixelType = model.PixelType;
                _outIsValid = true;
                _outStatusCode = "OK";
                _outStatusText = "供图：" + plan.Item.DisplayName + "（" + plan.ModeText + "）";

                // 7. 模板输出（显式发布，模板可丢失诊断，文档 E10）
                if (!string.IsNullOrEmpty(Settings.TemplateImageId))
                {
                    EnsureTemplateImage();
                    if (_templateImage != null)
                    {
                        var templateModel = Settings.ImageItems.FirstOrDefault(i => string.Equals(i.Id, Settings.TemplateImageId));
                        _outTemplatePath = templateModel != null ? templateModel.SourcePath : string.Empty;
                    }
                    else
                    {
                        _outStatusText += "；模板丢失（不自动替换）";
                    }
                }

                // 8. 顺序模式推进游标（循环取模；非循环到末尾报告序列结束，不复用图像）
                if (plan.Advance)
                {
                    _sequenceCursor++;
                    int count = plan.TotalCount;
                    if (!plan.Loop && _sequenceCursor >= count)
                    {
                        _outIsSequenceEnd = true;
                    }
                    if (plan.Loop && count > 0)
                    {
                        _sequenceCursor = _sequenceCursor % count;
                    }
                }

                _outElapsedMs = _execTimer.Elapsed.TotalMilliseconds;
                ChangeModuleRunStatus(eRunStatus.OK);
                return true;
            }
            catch (Exception ex)
            {
                _outStatusCode = "EXCEPTION";
                _outStatusText = ex.Message;
                Logger.GetExceptionMsg(ex);
                ChangeModuleRunStatus(eRunStatus.NG);
                return false;
            }
            finally
            {
                if (frame != null)
                {
                    _adapter.ReleaseImage(frame);
                }
                _outElapsedMs = _execTimer.Elapsed.TotalMilliseconds;
            }
        }

        /// <summary>输出注册（平台每周期回调；值来自输出快照字段）。</summary>
        public override void AddOutputParams()
        {
            base.AddOutputParams();
            if (_publisher == null)
            {
                _publisher = new VmOutputPublisher();
            }
            var bundle = new OpenFileOutputBundle
            {
                Image = _outImage,
                ImagePath = _outImagePath,
                SampleId = _outSampleId,
                Category = _outCategory,
                Width = _outWidth,
                Height = _outHeight,
                Channels = _outChannels,
                PixelType = _outPixelType,
                IsSequenceEnd = _outIsSequenceEnd,
                TemplateImage = _outIsValid ? _templateImage : null,
                TemplatePath = _outTemplatePath,
                IsValid = _outIsValid,
                StatusCode = _outStatusCode,
                StatusText = _outStatusText,
                ElapsedMs = _outElapsedMs
            };
            _publisher.Publish(bundle, (name, type, value, description) =>
                AddOutputParam(name, type, value, description));
        }

        private void ReleaseSuppliedImage()
        {
            if (_suppliedImage != null)
            {
                _adapter.ReleaseImage(_suppliedImage);
                _suppliedImage = null;
            }
        }

        private void ClearCycleOutputs()
        {
            _outImage = null;
            _outImagePath = string.Empty;
            _outSampleId = string.Empty;
            _outCategory = string.Empty;
            _outWidth = 0;
            _outHeight = 0;
            _outChannels = 0;
            _outPixelType = string.Empty;
            _outIsSequenceEnd = false;
            _outIsValid = false;
            _outStatusCode = string.Empty;
            _outStatusText = string.Empty;
            _outTemplatePath = string.Empty;
            _outElapsedMs = 0;
        }

        private void EnsureTemplateImage()
        {
            if (_templateImage != null)
            {
                return;
            }
            ImageItemModel templateModel;
            lock (_syncRoot)
            {
                templateModel = Settings.ImageItems.FirstOrDefault(i => string.Equals(i.Id, Settings.TemplateImageId));
            }
            if (templateModel == null || !File.Exists(templateModel.SourcePath))
            {
                return; // 模板丢失：不自动替换其他图像（文档 E10）
            }
            try
            {
                _templateImage = _adapter.LoadImage(templateModel.SourcePath);
            }
            catch (Exception)
            {
                _templateImage = null;
            }
        }

        private SamplePlan SelectSample()
        {
            List<ImageItemViewModel> snapshot;
            string selectedId;
            ImageInputMode mode;
            bool loopSequence;
            lock (_syncRoot)
            {
                snapshot = _ui.FilteredImages.ToList();
                selectedId = Settings.SelectedImageId;
                mode = Settings.ImageInputMode;
                loopSequence = Settings.LoopSequence;
            }

            if (snapshot.Count == 0)
            {
                return SamplePlan.Fail("NO_IMAGE", "图像清单为空（或被类别筛选过滤）");
            }

            bool loop = mode == ImageInputMode.SequentialLoop || (mode == ImageInputMode.Sequential && loopSequence);
            if (mode == ImageInputMode.Sequential && !loop && _sequenceCursor >= snapshot.Count)
            {
                return SamplePlan.Fail("SEQUENCE_END", "顺序供图已完成（共 " + snapshot.Count + " 张），已到末尾，不复用图像", true);
            }

            ImageItemViewModel target;
            bool advance = false;
            string modeText;
            if (mode == ImageInputMode.CurrentImage)
            {
                target = snapshot.FirstOrDefault(i => string.Equals(i.Id, selectedId)) ?? snapshot[0];
                modeText = "当前图像";
            }
            else
            {
                int index = _sequenceCursor;
                if (loop && snapshot.Count > 0)
                {
                    index = index % snapshot.Count;
                }
                index = Math.Min(Math.Max(index, 0), snapshot.Count - 1);
                target = snapshot[index];
                advance = true;
                modeText = loop ? "顺序循环" : "顺序";
            }

            string categoryName = ResolveCategoryName(target.Model.CategoryId);
            return SamplePlan.Success(target, categoryName, modeText, advance, loop, snapshot.Count);
        }

        private string ResolveCategoryName(string categoryId)
        {
            lock (_syncRoot)
            {
                var category = Settings.Categories.FirstOrDefault(c => string.Equals(c.Id, categoryId));
                return category != null ? category.Name : "未标注";
            }
        }

        private class SamplePlan
        {
            public bool Ok { get; private set; }
            public ImageItemViewModel Item { get; private set; }
            public string CategoryName { get; private set; }
            public string ModeText { get; private set; }
            public bool Advance { get; private set; }
            public bool Loop { get; private set; }
            public int TotalCount { get; private set; }
            public string StatusCode { get; private set; }
            public string StatusText { get; private set; }
            public bool IsSequenceEnd { get; private set; }

            public static SamplePlan Success(ImageItemViewModel item, string category, string modeText, bool advance, bool loop, int total)
            {
                return new SamplePlan { Ok = true, Item = item, CategoryName = category, ModeText = modeText, Advance = advance, Loop = loop, TotalCount = total };
            }

            public static SamplePlan Fail(string code, string text, bool sequenceEnd = false)
            {
                return new SamplePlan { Ok = false, StatusCode = code, StatusText = text, IsSequenceEnd = sequenceEnd };
            }
        }

        #endregion
    }

    /// <summary>预览图像事件参数（null = 清空显示）。</summary>
    public class PreviewImageEventArgs : EventArgs
    {
        public RImage Image { get; private set; }

        public PreviewImageEventArgs(RImage image)
        {
            Image = image;
        }
    }
}
```

---

### 文件 30: `ViewModels/RelayCommand.cs`

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

- **相对路径**: `ViewModels/RelayCommand.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.74 KB`
- **命名空间**: `Plugin.OpenFile.ViewModels`
- **核心类型**: `class ObservableObject`, `class RelayCommand`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.ComponentModel;
using System.Windows.Input;

namespace Plugin.OpenFile.ViewModels
{
    /// <summary>INotifyPropertyChanged 基类（ViewModel 层通知基础设施）。</summary>
    public abstract class ObservableObject : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler PropertyChanged;

        protected void OnPropertyChanged(string propertyName)
        {
            var handler = PropertyChanged;
            if (handler != null)
            {
                handler(this, new PropertyChangedEventArgs(propertyName));
            }
        }

        protected bool SetField<T>(ref T field, T value, string propertyName)
        {
            if (Equals(field, value)) return false;
            field = value;
            OnPropertyChanged(propertyName);
            return true;
        }
    }

    /// <summary>轻量命令实现（插件内自含，不依赖额外命令库）。</summary>
    public class RelayCommand : ICommand
    {
        private readonly Action<object> _execute;
        private readonly Predicate<object> _canExecute;

        public RelayCommand(Action<object> execute, Predicate<object> canExecute = null)
        {
            _execute = execute ?? throw new ArgumentNullException("execute");
            _canExecute = canExecute;
        }

        public bool CanExecute(object parameter)
        {
            return _canExecute == null || _canExecute(parameter);
        }

        public void Execute(object parameter)
        {
            _execute(parameter);
        }

        public event EventHandler CanExecuteChanged
        {
            add { CommandManager.RequerySuggested += value; }
            remove { CommandManager.RequerySuggested -= value; }
        }
    }
}
```

---

### 文件 31: `Views/OpenFileView.xaml.cs`

- **相对路径**: `Views/OpenFileView.xaml.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `4.32 KB`
- **命名空间**: `Plugin.OpenFile.Views`
- **核心类型**: `class OpenFileView`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Windows;
using System.Windows.Controls;
using Plugin.OpenFile.ViewModels;
using VM.Start.Core;

namespace Plugin.OpenFile.Views
{
    /// <summary>
    /// Plugin.OpenFile 主视图。
    /// 代码后置仅做：DataContext 获取、预览事件桥接、控件事件转发到 ViewModel 命令/方法；
    /// 不直接读取文件、不调用 HALCON、不发布平台输出（文档 §4.2 分层约束）。
    /// 主题：资源字典仅本地隐式语义样式，不合并固定主题（Light/Dark 跟随宿主）。
    /// </summary>
    public partial class OpenFileView : ModuleViewBase
    {
        private OpenFileViewModel _vm;

        public OpenFileView()
        {
            InitializeComponent();
            Loaded += OnViewLoaded;
            Unloaded += OnViewUnloaded;
        }

        private void OnViewLoaded(object sender, RoutedEventArgs e)
        {
            _vm = DataContext as OpenFileViewModel;
            if (_vm == null)
            {
                return;
            }
            _vm.PreviewImageChanged -= OnPreviewImageChanged;
            _vm.PreviewImageChanged += OnPreviewImageChanged;
            // 恢复类别筛选选择（持久化值）
            FilterCombo.SelectedValue = _vm.CurrentFilterCategoryId;
        }

        /// <summary>关闭 View 停止订阅（L02：不再刷新失效控件）。</summary>
        private void OnViewUnloaded(object sender, RoutedEventArgs e)
        {
            if (_vm != null)
            {
                _vm.PreviewImageChanged -= OnPreviewImageChanged;
            }
            _vm = null;
        }

        /// <summary>
        /// 编辑器本地渲染：先 window.Image = image 再 DispImageFitImage()（台账 §4 confirmed）。
        /// 与工作流显示彼此隔离（文档 §4.2）。null 表示清空请求：保留最后画面，不向控件传 null。
        /// </summary>
        private void OnPreviewImageChanged(object sender, PreviewImageEventArgs e)
        {
            if (e == null || e.Image == null)
            {
                return;
            }
            PreviewWindow.Image = e.Image;
            PreviewWindow.DispImageFitImage();
        }

        private void ImageList_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm == null)
            {
                return;
            }
            vm.SelectImage(e.AddedItems.Count > 0 ? e.AddedItems[0] as ImageItemViewModel : null);
        }

        private void DocumentList_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm == null)
            {
                return;
            }
            vm.SelectDocument(e.AddedItems.Count > 0 ? e.AddedItems[0] as DocumentItemViewModel : null);
        }

        private void FilterCombo_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm == null)
            {
                return;
            }
            vm.ApplyCategoryFilter(FilterCombo.SelectedValue as string);
        }

        private void RemarkBox_LostFocus(object sender, RoutedEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm != null)
            {
                vm.CommitRemark();
            }
        }

        private void BrowseExport_Click(object sender, RoutedEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm != null)
            {
                vm.BrowseExportDirectory();
            }
        }

        /// <summary>拖拽导入分流（图像/文档），逻辑在 ViewModel.AddDroppedFiles。</summary>
        private void View_Drop(object sender, DragEventArgs e)
        {
            var vm = _vm ?? (DataContext as OpenFileViewModel);
            if (vm == null || !e.Data.GetDataPresent(DataFormats.FileDrop))
            {
                return;
            }
            var paths = e.Data.GetData(DataFormats.FileDrop) as string[];
            if (paths != null && paths.Length > 0)
            {
                vm.AddDroppedFiles(paths);
            }
        }
    }
}
```

---

### 文件 32: `Properties/DesignTimeResources.xaml`

- **相对路径**: `Properties/DesignTimeResources.xaml`
- **文件类型**: `WPF/XAML 文件`
- **文件大小**: `1.17 KB`
- **概要**: WPF/XAML 界面布局或资源定义文件

```xml
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                    xmlns:mah="http://metro.mahapps.com/winfx/xaml/controls">
    <!-- 仅服务 XAML 设计器预览（补齐 MahApps/HandyControl/宿主样式设计时上下文）；
         不进运行时合并（主题合规：运行时 View 禁止合并固定主题字典）。 -->
    <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="pack://application:,,,/HandyControl;component/Themes/SkinDark.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/HandyControl;component/Themes/Theme.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Controls.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Fonts.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Themes/Dark.Purple.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/VM.Start;component/Assets/Collection.xaml" />
    </ResourceDictionary.MergedDictionaries>
</ResourceDictionary>
```

---

### 文件 33: `app.config`

- **相对路径**: `app.config`
- **文件类型**: `XML 配置文件`
- **文件大小**: `172 B`
- **概要**: XML 配置文件

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7.2" />
  </startup>
</configuration>
```

---

### 文件 34: `packages.config`

- **相对路径**: `packages.config`
- **文件类型**: `XML 配置文件`
- **文件大小**: `370 B`
- **概要**: XML 配置文件

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  <package id="ControlzEx" version="5.0.0" targetFramework="net472" />
  <package id="HandyControl" version="3.4.0" targetFramework="net472" />
  <package id="MahApps.Metro" version="2.0.0" targetFramework="net472" />
  <package id="Microsoft.Xaml.Behaviors.Wpf" version="1.1.19" targetFramework="net472" />
</packages>
```

---

