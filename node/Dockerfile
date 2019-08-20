FROM node:10.16.3-buster
RUN npm install strapi@beta -g
RUN strapi new my-app --quickstart
COPY hook.json my-app/config/hook.json
WORKDIR /my-app
ENV AWS_ACCESS_KEY_ID=Q3AM3UQ867SPQQA43P2F
ENV AWS_SECRET_ACCESS_KEY=zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG
RUN npm i aws-sdk 
RUN npm install
RUN npm i strapi-provider-upload-aws-s3-custom-domain
COPY region_config_data.json /my-app/node_modules/aws-sdk/lib/region_config_data.json
COPY .aws /home/.aws
RUN yarn build
EXPOSE 1337
ENTRYPOINT yarn develop