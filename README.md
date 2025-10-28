<h1>Hancom Office Viewer</h1>

[![](https://jitpack.io/v/MCT-LIB/HancomOfficeViewerPublic.svg)](https://jitpack.io/#MCT-LIB/HancomOfficeViewerPublic)

This project delivers a lightweight, high-performance library for reading and rendering Hancom Office documents (.hwp, .hwpx) directly on Android.
It provides a clean and flexible API that allows developers to integrate document viewing, parsing, and text extraction into their applications with minimal configuration.
<h4>✨ Features</h4>
✅ Read and parse Hancom HWP/HWPX document structures<br>
✅ Extract text, tables, and equations from content<br>
✅ Render pages and graphic objects (shapes, pictures, etc.)<br>
✅ Support for embedded styles, paragraphs, and annotations<br>
✅ Modular design for easy integration with custom renderers<br>

<h4>🧩 Compatibility</h4>
Android API 24+<br>
Compatible with Android Studio and Gradle build system<br>

<h4>⚙️ Usage:</h4>
<h6>Step 1: implementation library</h6>
<pre>
  implementation 'com.github.MCT-LIB:HancomOfficeViewerPublic:TAG'
</pre>
<h6>Step 2: add renderer view to your layout</h6>
<pre>
  &lt;com.mct.office.renderer.viewer.RendererView
      android:id="@+id/renderer_view"
      android:layout_width="match_parent"
      android:layout_height="match_parent" /&gt;
</pre>
<h6>Step 3: code</h6>
<pre>
  // create a renderer match your file extension
  HwpRenderer renderer = new HwpRenderer(App.getInstance());
  HwpxRenderer renderer = new HwpxRenderer(App.getInstance());<br>
  // set renderer to view
  int pageSize = 1080;
  RendererView rendererView = findViewById(R.id.renderer_view);<br>
  String path = "";
  rendererView.init(renderer, path, pageSize);<br>
  File file = new File("");
  rendererView.init(renderer, file, pageSize);<br>
  InputStream inputStream = null;
  rendererView.init(renderer, inputStream, pageSize);
</pre>
<pre>
  // clear resource if need
  @Override
  protected void onDestroy() {
    super.onDestroy();
    if (rendererView != null) {
      rendererView.destroy();
    }
  }
</pre>

 
