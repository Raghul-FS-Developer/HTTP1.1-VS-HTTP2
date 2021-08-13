The HTTP/1.1 To HTTP/2 Transition
The breaking point in HTTP/1.1 was reached well before the 2015 introduction of HTTP/2. In fact, Google was working on it’s own replacement for HTTP/1.1 since the early 2010s, called SPDY (pronounced “speedy”). This protocol used the existing infrastructure built for HTTP/1.1, but modified how the requests worked over the infrastructure. SPDY used multiplexing to download multiple resources efficiently over a single connection, and could be “back-ported” to existing applications with a translation layer.

It makes sense that Google would take the lead on this, as they had been developing increasingly complex web-based applications that operated more like desktop applications than websites, like GMail and Google Apps. In fact, the SPDY protocol was so well-designed, w3 used it as the basis for HTTP/2.

So, in 2015, w3 officially adopted the HTTP/2 specification based on SPDY, and all major browsers began supporting the protocol.

Why HTTP/2 Is Faster Than HTTP/1.1
Today, the concept of “webpages” is anachronistic, in much the same way as “videotaping” something with your smartphone. Modern websites function much more like applications, with a constant two-way stream of data being an essential part of their functionality.

For example, when you’re typing something in a Google Doc, as I am typing this article right now, every keystroke sends data to Google’s servers. Google’s servers process that data, and then send updates back to your browser with the text you’ve typed, along with other helpful information like suggestions, the last edit status of the document, and much more. Over HTTP/1.1, each of your keypresses would initiate a new connection to the server, to send each character you typed over the wire. Then, your browser would have to constantly “ping” Google’s server to see if the status of the document changed, to add the character to the screen you’re looking at. That’s a boatload of connections, and each one takes precious time.

With HTTP/2 though, it’s essentially a constant two-way stream over a single connection. Google’s server is always listening for data coming from your browser, and your browser is always listening for data to come back from Google. There’s no more send data, wait for response, update the screen, send more data, wait for a response, etc. Instead, everything happens in real-time. In this way, a web “page” like a Google Doc can update itself so frequently as to feel like a native application on your computer.

These are the high-level differences between HTTP1 and HTTP2:

HTTP2 is binary, instead of textual
HTTP2 is fully multiplexed, instead of ordered and blocking
HTTP2 can, therefore, use one connection for parallelism
HTP2 uses header compression to reduce overhead
HTTP2 allows servers to “push” responses proactively into client caches
