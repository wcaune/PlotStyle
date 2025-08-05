# PlotStyle
Root, Python and others plotting style.


## ROOT plotting script
In the `.cc` file, add 

```cpp
void dib()
{
 // Defaults to classic style, but that's OK, we can fix it
  TStyle* novaStyle = new TStyle("novaStyle", "NOvA Style");

  // Centre title
  novaStyle->SetTitleAlign(22);
  novaStyle->SetTitleX(.45);
  novaStyle->SetTitleY(.95);
  novaStyle->SetTitleBorderSize(0);

  // No info box
 // novaStyle->SetOptStat(0);

  //set the background color to white
  novaStyle->SetFillColor(10);
  novaStyle->SetFrameFillColor(10);
  novaStyle->SetCanvasColor(10);
  novaStyle->SetPadColor(10);
  novaStyle->SetTitleFillColor(0);
  novaStyle->SetStatColor(10);

  // Don't put a colored frame around the plots
  novaStyle->SetFrameBorderMode(0);
  novaStyle->SetCanvasBorderMode(0);
  novaStyle->SetPadBorderMode(0);

  // Set the default line color for a fit function to be red
  novaStyle->SetFuncColor(kRed);

  // Marker settings
  //  novaStyle->SetMarkerStyle(kFullCircle);

  // No border on legends
  novaStyle->SetLegendBorderSize(0);

  // Disabled for violating NOvA style guidelines
  // Scientific notation on axes
  //  TGaxis::SetMaxDigits(3);

  // Axis titles
  novaStyle->SetTitleSize(.055, "xyz");
  novaStyle->SetTitleOffset(.8, "xyz");
  // More space for y-axis to avoid clashing with big numbers
//  novaStyle->SetTitleOffset(.9, "y");
  novaStyle->SetTitleOffset(.9, "y");
  // This applies the same settings to the overall plot title
  novaStyle->SetTitleSize(.055, "");
  novaStyle->SetTitleOffset(.8, "");
  // Axis labels (numbering)
  novaStyle->SetLabelSize(.05, "xyz");
  novaStyle->SetLabelOffset(.005, "xyz");

  // Thicker lines
  novaStyle->SetHistLineWidth(3);
  novaStyle->SetFrameLineWidth(3);
  novaStyle->SetFuncWidth(3);

  // Set the number of tick marks to show
  novaStyle->SetNdivisions(506, "xyz");

  // Set the tick mark style
  novaStyle->SetPadTickX(1);
  novaStyle->SetPadTickY(1);
  
  //png scale
 // novaStyle->SetImageScaling(13.);

  // Fonts 
  
  const int kNovaFont = 132;
  novaStyle->SetStatFont(kNovaFont);
  novaStyle->SetLabelFont(kNovaFont, "xyz");
  novaStyle->SetTitleFont(kNovaFont, "xyz");
  novaStyle->SetTitleFont(kNovaFont, ""); // Apply same setting to plot titles
  novaStyle->SetTextFont(kNovaFont);
  novaStyle->SetLegendFont(kNovaFont);

 gROOT->SetStyle("novaStyle");
 gStyle->SetOptStat(0);
 // 
```
