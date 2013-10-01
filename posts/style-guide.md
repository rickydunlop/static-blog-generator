title: Style guide
date: 2013-10-01
published: true

## Style guide

# This is an h1 header
## This is an h2 header
### This is an h3 header
#### This is an h4 header
##### This is an h5 header

This is a paragraph

**Bold text**

_emphasised text_

### List
*   Abacus
    * answer
*   Bubbles
    1.  bunk
    2.  bupkis
        * BELITTLER
    3. burper
*   Cunning

### Code sample

    :::python
    from urlparse import urljoin
    from flask import request
    from werkzeug.contrib.atom import AtomFeed


    def make_external(url):
        return urljoin(request.url_root, url)


    @app.route('/recent.atom')
    def recent_feed():
        feed = AtomFeed('Recent Articles',
                        feed_url=request.url, url=request.url_root)
        articles = Article.query.order_by(Article.pub_date.desc()) \
                          .limit(15).all()
        for article in articles:
            feed.add(article.title, unicode(article.rendered_text),
                     content_type='html',
                     author=article.author.name,
                     url=make_external(article.url),
                     updated=article.last_update,
                     published=article.published)
        return feed.get_response()