# HappyJoyCMS
HappyJoyCMS is a modular PHP CMS featuring Twig templating, multi-language support, SEO-friendly routing, role-based user management, and optimized caching. With a customizable plugin system, DI support, and “Joy Mode” UI enhancements, HappyJoyCMS simplifies web development while adding a touch of fun.

# Warning

This project is heavily AI influenced.

# Initial Prompt

## Project Prompt: Develop a Modular, Multilingual CMS with Step-by-Step Guidance

### Role Context
You are a senior software developer tasked with building a modular, scalable, and secure Content Management System (CMS) with multilingual capabilities and customizable features. This project will be developed in an iterative, step-by-step manner, with detailed explanations and code comments at each stage. The project will emphasize clean, well-documented code, making it easy to maintain, extend, and scale.

**Core Libraries**:
- **PHP-DI**: For dependency injection across core components.
- **Parsedown**: For rendering Markdown content.
- **Twig**: For templating and view rendering.
- **FastRoute**: For efficient, dynamic routing with automatic route discovery and caching.
- **PHPAuth**: Used as a plugin, “UsersPlugin,” to handle user authentication and role-based access control.

---

### Project Overview
Your goal is to develop a customizable, multilingual CMS focused on modularity, performance, and security. Using an MVC (Model-View-Controller) structure, the CMS will support dynamic route discovery, caching, and a plugin architecture to extend functionality. This project will be guided step-by-step, where you’ll be asked to confirm each completed step before moving on to the next.

---

### Guidance and Step-by-Step Process

1. **Detailed Code and Comments**: Each step will include clear, well-commented code to illustrate functionality and ensure understanding.
2. **Confirmation of Progress**: After implementing each step, confirm completion and understanding before proceeding.
3. **Iterative Development**: Each step builds upon the previous one, ensuring the CMS is constructed in a logical, modular, and scalable manner.

---

### Requirements

#### Core Architecture

1. **MVC Structure**  
   - Use MVC to separate concerns between data handling (models), HTML templates (views), and request handling (controllers).
   - Each component should be clearly structured with its role well-defined and documented.

2. **Dependency Injection with PHP-DI**  
   - Implement PHP-DI for dependency injection to promote modular, scalable, and maintainable code.

3. **Dynamic Routing with FastRoute**  
   - Configure FastRoute with an automatic route discovery mechanism, scanning controllers for annotated routes.
   - Cache generated routes for efficiency, storing them in a cache file (e.g., `cache/routes.php`).
   - Support multilingual paths with SEO-friendly slugs, with fallbacks for untranslated content.

4. **Templating with Twig**  
   - Use Twig for templating to keep the view layer organized, reusable, and optimized for SEO.

5. **Plugin System**  
   - Design a plugin architecture allowing users to extend CMS functionality with minimal configuration.
   - Integrate "UsersPlugin" using PHPAuth for user authentication and role-based access control.

#### Content Management

1. **Multilingual Content Support**  
   - Organize and store multilingual content in structured directories, with dynamic language switching.

2. **Markdown Processing with Parsedown**  
   - Use Parsedown for rendering Markdown content as HTML, simplifying content creation.

#### Optimization and Security

1. **Caching**  
   - Implement caching for parsed HTML, Markdown, and routes, with cache invalidation on updates.

2. **Secure Coding Practices**  
   - Apply input sanitization, CSRF protection, and secure session handling.

3. **URL and Directory Security with `.htaccess`**  
   - Configure `.htaccess` to enforce HTTPS and secure sensitive directories.

#### Robustness and Maintainability

1. **Testing**  
   - Implement unit and integration tests to validate functionality.

2. **Error Logging and Monitoring**  
   - Set up logging for runtime errors, with custom error pages for 404, 500, etc.

3. **Backup and Data Recovery**  
   - Develop an automated backup plan for essential data.

4. **Version Control and CI/CD Pipeline**  
   - Use Git for version control with branching strategies, and CI/CD pipelines for deployment.

---

### Directory Structure

```plaintext
/project-root
├── cms                          # Core CMS functionality, organized by MVC
│   ├── controller               # Handles request logic (automatically scanned for routes)
│   ├── model                    # Manages data operations
│   ├── view                     # Twig templates for views
│   ├── service                  # Services like Cache, Language, PluginManager
│   ├── annotations              # Custom annotations (e.g., Route)
│   │   └── Route.php            # Annotation class for route definitions
│   ├── Container.php            # PHP-DI container for dependency injection
│   ├── Config.php               # Configuration handler
│   └── Router.php               # FastRoute setup with dynamic route loading and caching
├── user                         # User-specific content, plugins, and configurations
│   ├── content                  # Stores content files (e.g., Markdown)
│   ├── plugin                   # Directory for custom plugins, including "UsersPlugin"
│   ├── lang                     # Language files for UI strings
│   ├── account                  # User account data
│   └── config                   # User-specific configuration files
├── cache                        # Cache storage for parsed HTML, generated routes, and other data
│   ├── routes.php               # Cache file for dynamically generated routes
│   ├── post                     # Cached content for posts
│   └── other                    # Additional cached data as needed
├── public                       # Public-facing files (CSS, JS, main entry point)
│   ├── assets                   # Static assets (CSS, JavaScript, images)
│   ├── .htaccess                # Security and URL rewrite rules
│   └── index.php                # Main entry point for the CMS
├── vendor                       # Composer dependencies
└── composer.json                # Composer configuration for autoloading and dependencies
```

---

### Iterative Step-by-Step Implementation Guide

This guide takes you through each stage incrementally, where each step includes commented code and requires confirmation before moving forward.

#### **1. Project Initialization**
   - **Create `index.php`**: Start with a minimal `index.php` in `public` as the main entry point for requests.
   - **Set Up Basic Routing**: Configure simple routing in `index.php` using FastRoute.
   - **Testing**: Confirm that `index.php` is accessible and can handle basic routing.
   - **Confirmation**: Once this step is complete and tested, confirm to proceed to the next step.

#### **2. Directory Structure and Autoloading**
   - **Organize Core Folders**: Set up `cms` with `controller`, `model`, `view`, and `service`.
   - **Composer Autoloading**: Use Composer for class autoloading and dependency management.
   - **Testing**: Ensure autoloading works by loading a sample class.
   - **Confirmation**: Confirm completion of this step to move on.

#### **3. PHP-DI for Dependency Injection**
   - **Implement `Container.php`**: Set up PHP-DI for dependency injection.
   - **Register Dependencies**: Inject core services like Twig, Parsedown, and FastRoute.
   - **Testing**: Verify that dependencies are correctly injected.
   - **Confirmation**: Confirm to proceed to the next step.

#### **4. Dynamic Route Discovery and Caching with FastRoute**
   - **Router Setup with Annotations**: Configure `Router.php` to scan for route annotations.
   - **Route Caching**: Cache routes in `cache/routes.php`.
   - **Testing**: Test automatic route discovery, caching, and dispatching.
   - **Confirmation**: Confirm successful setup to move forward.

#### **5. Twig Templating Integration**
   - **Create Basic Twig Templates**: Set up templates in `view`.
   - **Render Views through Twig**: Use Twig for dynamic content rendering.
   - **Testing**: Confirm data is correctly passed to templates.
   - **Confirmation**: Proceed upon confirmation.

#### **6. Multilingual Content and Routing**
   - **i18n Routing**: Enable multilingual routing with FastRoute.
   - **Language Files**: Set up `user/lang`.
   - **Testing**: Verify dynamic language switching based on URL parameters.
   - **Confirmation**: Confirm completion of this step.

#### **7. Plugin System and "UsersPlugin"**
   - **Plugin Manager**: Create `PluginManager` to load plugins.
   - **UsersPlugin with PHPAuth**: Integrate PHPAuth for authentication.
   - **Testing**: Confirm plugin integration and user management functions.
   - **Confirmation**: Confirm to continue.

#### **8. Markdown Content with Parsedown**
   - **Parsedown Integration**: Use Parsedown for rendering Markdown.
   - **Testing**: Verify Markdown renders as HTML.
   - **Confirmation**: Confirm to proceed.

#### **9. Caching Mechanism**
   - **Cache Service**: Develop caching for parsed HTML and routes.
   - **Testing**: Verify caching improves performance and updates correctly.
   - **Confirmation**: Confirm to continue.

#### **10. Security Enhancements**
   - **Input Sanitization and CSRF Protection**: Implement secure practices.
   - **Testing**: Validate security measures.
   - **Confirmation**: Confirm this step to move forward.

#### **11. URL Security with `.htaccess`**
   - **Configure `.htaccess`**: Set up clean URLs and HTTPS enforcement.
   - **Testing**: Test URL security.
   - **Confirmation**: Confirm completion.

#### **12. Testing Suite**
   - **Unit and Integration Tests**: Implement PHPUnit tests.
   - **Testing**: Ensure stability.
   - **Confirmation**: Confirm before proceeding.

#### **13. Logging and Error Handling**
   - **Logging Service**: Set up error logging.
   - **Testing**: Confirm logs capture errors.
   - **Confirmation**: Confirm before next step.

#### **14. Backup and Recovery**
   - **Automated Backups**: Develop scripts for backups.
   - **Testing**: Perform recovery tests.
   - **Confirmation**: Confirm completion.

#### **15. Version Control and CI/CD**
   - **Git for Version Control**: Use branching for features.
   - **CI/CD Pipeline**: Automate testing and deployment.
   - **Testing**: Confirm deployment.
   - **Confirmation**: Confirm the final step.
