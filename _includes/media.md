<style>
    .articles-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 30px;
        margin: 30px 0;
    }
    
    .article-card {
        border-radius: 8px;
        overflow: hidden;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        transition: transform 0.2s ease-in-out;
        height: 100%;
        display: flex;
        background-color: #fcfcfc;
        flex-direction: column;
    }
    
    .article-card:hover {
        transform: translateY(-5px);
    }
    
    .article-image-container {
        height: 200px;
        overflow: hidden;
    }
    
    .article-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    
    .article-content {
        padding: 15px;
        flex-grow: 1;
        display: flex;
        flex-direction: column;
    }
    
    .article-title {
        font-size: 1.2rem;
        margin-bottom: 10px;
        font-weight: 600;
    }
    
    .article-author {
        color: #666;
        font-size: 0.9rem;
        margin-bottom: 5px;
    }
    
    .article-link {
        margin-top: auto;
        text-decoration: none;
        color: #0066cc;
        font-weight: 500;
    }
    
    .article-link:hover {
        text-decoration: underline;
    }
    
    @media (max-width: 768px) {
        .articles-container {
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        }
    }
</style>

<div class="articles-container">
    {% for article in site.data.articles %}
    <div class="article-card">
        <a href="{{ article.url }}" target="_blank">
            <div class="article-image-container">
                <img src="{{ article.image }}" alt="{{ article.title }}" class="article-image">
            </div>
            <div class="article-content">
                <h2 class="article-title"> {{ article.title }} </h2>
                <p class="article-author">By {{ article.author }} {{ article.connector}} <i>{{ article.source }}</i>, {{ article.year }}</p>
            </div>
        </a>
    </div>
    {% endfor %}
</div>