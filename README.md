# mdl-et718-20220511-rails-hr-repo


rails generate model Article title:string text:text
rails g scaffold Resume name image_url role location email phone



<%= link_to 'My Blog', controller: 'articles' %>
<%= link_to 'Resume Database', controller: 'resumes' %>


rails generate model Comment commenter:string body:text article:references
rails g model Skill title level resume:references




resources :articles do
  resources :comments
end

resources :resumes do
  resources :skills
end




rails generate controller Comments
rails generate controller Skills



  def create
    @article = Article.find(params[:article_id])
    @comment = @article.comments.create(comment_params)
    redirect_to article_path(@article)
  end
 
  private
    def comment_params
      params.require(:comment).permit(:commenter, :body)
    end
    
    
    def create
    @resume = Resume.find(params[:resume_id])
    @skill = @resume.skills.create(skill_params)
    redirect_to resume_path(@resume)
  end
 
  private
    def skill_params
      params.require(:skill).permit(:title, :level)
    end
    
    
    rails generate model Comment commenter:string body:text article:references
    rails generate model Language title level resume:references
    
    
    
    rails generate controller Comments
    rails generate controller Languages
    
    
    
    
    
    
    
    
    
    
    
    
    
    