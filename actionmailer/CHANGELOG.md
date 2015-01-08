*   Added support for ActionMailer::Base#mail to take a template_name option even when passed a block.

        class MyMailer < ActionMailer::Base
          def hello
            mail(template_name: 'goodbye') do |format|
              format.html # Will render app/views/my_mailer/goodbye.html.erb
              format.text { render } # Will render app/views/my_mailer/hello.text.erb
            end
          end
        end

    *Isaac Betesh*

*   Allow Action Mailer classes to configure their delivery job.

        class MyMailer < ApplicationMailer
          self.delivery_job = MyCustomDeliveryJob

          ...
        end

    *Matthew Mongeau*


Please check [5-1-stable](https://github.com/rails/rails/blob/5-1-stable/actionmailer/CHANGELOG.md) for previous changes.
