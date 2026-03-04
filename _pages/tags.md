<main class="tags-page">
    <div class="tag-cloud" style="margin-bottom: 2rem; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
        <h4 style="margin-top: 0;">Jump to Topic:</h4>
        {% capture tags %}
          {% for tag in site.tags %}
            {{ tag[0] }}
          {% endfor %}
        {% endcapture %}
        {% assign sortedtags = tags | split: ' ' | sort %}
        
        {% for tag in sortedtags %}
          <a href="#{{ tag }}" style="margin-right: 15px; text-decoration: none; font-weight: bold; color: #376a8c;">
            #{{ tag | capitalize }}
          </a>
        {% endfor %}
    </div>

    <hr>

    <div class="pure-g">
        {% for tag in site.tags %}
        <div class="pure-u-1 tags" style="margin-bottom: 2rem;">
            <h3 id="{{ tag | first }}" style="border-bottom: 2px solid #376a8c; display: inline-block; padding-right: 20px;">
               <i class="fas fa-hashtag"></i> {{ tag | first | capitalize }}
            </h3>
            <ul style="list-style: square; padding-left: 20px;">
            {% for post in tag.last %}
                <li style="margin-bottom: 8px;">
                    <a href="{{ post.url | relative_url }}" style="font-size: 1.1rem;">{{ post.title }}</a>
                    <small style="color: #666; margin-left: 10px;">({{ post.date | date: "%Y" }})</small>
                </li>
            {% endfor %}
            </ul>
        </div>
        {% endfor %}
    </div>
</main>
