// ArenaAI Chat — Native iOS Wrapper (for .IPA sideloading)
// How to use: Xcode → New App (SwiftUI) → replace ContentView.swift with this file
// → drag index.html + icon.png into the project → Run on your iPhone.

import SwiftUI
import WebKit

@main
struct ArenaAIChatApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}

struct ContentView: View {
    var body: some View {
        ZStack {
            Color(red: 0.04, green: 0.04, blue: 0.06).ignoresSafeArea()
            WebView()
        }
    }
}

struct WebView: UIViewRepresentable {
    func makeUIView(context: Context) -> WKWebView {
        let config = WKWebViewConfiguration()
        config.defaultWebConfiguration.dataStore = .default()
        config.preferences.javaScriptCanOpenWindowsAutomatically = false
        let webView = WKWebView(frame: .zero, configuration: config)
        webView.scrollView.contentInsetAdjustmentBehavior = .never
        webView.isOpaque = false
        webView.backgroundColor = .clear
        webView.navigationDelegate = context.coordinator
        // Load bundled index.html (offline-first)
        if let url = Bundle.main.url(forResource: "index", withExtension: "html") {
            webView.loadFileURL(url, allowing: url.deletingLastPathComponent())
        } else {
            // Fallback: load your hosted URL here
            // webView.load(URLRequest(url: URL(string: "https://YOUR-NETLIFY-URL.netlify.app")!))
        }
        return webView
    }

    func updateUIView(_ uiView: WKWebView, context: Context) {}

    func makeCoordinator() -> Coordinator { Coordinator(self) }

    class Coordinator: NSObject, WKNavigationDelegate {
        var parent: WebView
        init(_ parent: WebView) { self.parent = parent }
        // Allow external links to open in Safari
        func webView(_ webView: WKWebView, decidePolicyFor navigationAction: WKNavigationAction, decisionHandler: @escaping (WKNavigationAction.Policy) -> Void) {
            if let url = navigationAction.request.url, navigationAction.navigationType == .linkClicked,
               url.scheme?.hasPrefix("http") == true {
                UIApplication.shared.open(url)
                decisionHandler(.cancel)
            } else {
                decisionHandler(.allow)
            }
        }
    }
}
