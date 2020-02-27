

import org.slf4j.Logger;

import org.slf4j.LoggerFactory;

import org.springframework.context.annotation.Bean;

import org.springframework.context.annotation.Configuration;

import springfox.documentation.builders.ApiInfoBuilder;

import springfox.documentation.builders.RequestHandlerSelectors;

import springfox.documentation.service.ApiInfo;

import springfox.documentation.spi.DocumentationType;

import springfox.documentation.spring.web.plugins.Docket;

@SuppressWarnings("deprecation")

@Configuration

public class Appconfig {

            private static final Logger LOG = LoggerFactory.getLogger(Appconfig.class);

            @Bean

            public Docket enableSwaggers() {

                  return new Docket(DocumentationType.SWAGGER_2)

                      .useDefaultResponseMessages(false)

                      .select()

                     .apis(RequestHandlerSelectors.basePackage("rest"))

                     .build()

                     .apiInfo(apiEndPointsInfo());

               }

            

            private ApiInfo apiEndPointsInfo() {

        return new ApiInfoBuilder().title("Emp REST API")

            .build();

    }

} 


