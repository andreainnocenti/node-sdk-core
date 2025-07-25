## API Report File for "ibm-cloud-sdk-core"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

/// <reference types="node" />

import { GenericAbortSignal as AbortSignal_2 } from 'axios';
import { AxiosInstance } from 'axios';
import type { CookieJar } from 'tough-cookie';
import { Debugger } from 'debug';
import { OutgoingHttpHeaders } from 'http';
import { Stream } from 'stream';

export { AbortSignal_2 as AbortSignal }

// @public
export function atLeastOne(...args: any): boolean;

// @public
export function atMostOne(...args: any): boolean;

// @public
export class Authenticator implements AuthenticatorInterface {
    constructor();
    // Warning: (ae-forgotten-export) The symbol "AuthenticateOptions" needs to be exported by the entry point index.d.ts
    authenticate(requestOptions: AuthenticateOptions): Promise<void>;
    authenticationType(): string;
    static AUTHTYPE_BASIC: string;
    // (undocumented)
    static AUTHTYPE_BEARERTOKEN: string;
    // (undocumented)
    static AUTHTYPE_CONTAINER: string;
    // (undocumented)
    static AUTHTYPE_CP4D: string;
    // (undocumented)
    static AUTHTYPE_IAM: string;
    // (undocumented)
    static AUTHTYPE_IAM_ASSUME: string;
    // (undocumented)
    static AUTHTYPE_MCSP: string;
    // (undocumented)
    static AUTHTYPE_MCSPV2: string;
    // (undocumented)
    static AUTHTYPE_NOAUTH: string;
    // (undocumented)
    static AUTHTYPE_UNKNOWN: string;
    // (undocumented)
    static AUTHTYPE_VPC: string;
}

// @public
export interface AuthenticatorInterface {
    authenticate(requestOptions: AuthenticateOptions): Promise<void>;
    authenticationType(): string;
}

// @public
export class BaseService {
    constructor(userOptions: UserOptions);
    // Warning: (ae-forgotten-export) The symbol "BaseServiceOptions" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    protected baseOptions: BaseServiceOptions;
    protected configureService(serviceName: string): void;
    static convertModel(input: any, converterFn: any, isMap?: boolean): any;
    protected createRequest(parameters: any): Promise<any>;
    protected createRequestAndDeserializeResponse(parameters: any, deserializerFn: (any: any) => any, isMap?: boolean): Promise<any>;
    // (undocumented)
    static DEFAULT_SERVICE_NAME: string;
    // (undocumented)
    static DEFAULT_SERVICE_URL: string;
    disableRetries(): void;
    // Warning: (ae-forgotten-export) The symbol "RetryOptions" needs to be exported by the entry point index.d.ts
    enableRetries(retryOptions?: RetryOptions): void;
    getAuthenticator(): any;
    getHttpClient(): AxiosInstance;
    setDefaultHeaders(headers: OutgoingHttpHeaders): void;
    setEnableGzipCompression(setting: boolean): void;
    setServiceUrl(url: string): void;
}

// @public
export class BasicAuthenticator extends Authenticator {
    // Warning: (ae-forgotten-export) The symbol "Options" needs to be exported by the entry point index.d.ts
    constructor(options: Options);
    authenticate(requestOptions: AuthenticateOptions): Promise<void>;
    authenticationType(): string;
    // (undocumented)
    protected authHeader: {
        Authorization: string;
    };
    // (undocumented)
    protected requiredOptions: string[];
}

// @public
export class BearerTokenAuthenticator extends Authenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_2" needs to be exported by the entry point index.d.ts
    constructor(options: Options_2);
    authenticate(requestOptions: AuthenticateOptions): Promise<void>;
    authenticationType(): string;
    // (undocumented)
    protected requiredOptions: string[];
    setBearerToken(bearerToken: string): void;
}

// @public
export function buildRequestFileObject(fileParam: FileWithMetadata): Promise<FileObject>;

// @public
export function checkCredentials(obj: any, credsToCheck: string[]): Error | null;

// @public
export class CloudPakForDataAuthenticator extends TokenRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_4" needs to be exported by the entry point index.d.ts
    constructor(options: Options_4);
    authenticationType(): string;
    // (undocumented)
    protected requiredOptions: string[];
    // (undocumented)
    protected tokenManager: Cp4dTokenManager;
}

// @public
export function computeBasicAuthHeader(username: string, password: string): string;

// @public (undocumented)
export function constructFilepath(filepath: string): string;

// @public
export function constructServiceUrl(parameterizedUrl: string, defaultUrlVariables: Map<string, string>, providedUrlVariables: Map<string, string> | null): string;

// @public
export class ContainerAuthenticator extends IamRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_8" needs to be exported by the entry point index.d.ts
    constructor(options: Options_8);
    authenticationType(): string;
    getRefreshToken(): string;
    setCrTokenFilename(crTokenFilename: string): void;
    setIamProfileId(iamProfileId: string): void;
    setIamProfileName(iamProfileName: string): void;
    // (undocumented)
    protected tokenManager: ContainerTokenManager;
}

// @public
export class ContainerTokenManager extends IamRequestBasedTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_7" needs to be exported by the entry point index.d.ts
    constructor(options: Options_7);
    protected getCrToken(): string;
    getRefreshToken(): string;
    protected requestToken(): Promise<any>;
    setCrTokenFilename(crTokenFilename: string): void;
    setIamProfileId(iamProfileId: string): void;
    setIamProfileName(iamProfileName: string): void;
}

// @public (undocumented)
export const contentType: {
    fromFilename: (file: String | File | FileObject | NodeJS.ReadableStream | Buffer) => string;
    fromHeader: (buffer: Buffer) => string;
};

// @public
export class Cp4dTokenManager extends JwtTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_3" needs to be exported by the entry point index.d.ts
    constructor(options: Options_3);
    // (undocumented)
    protected requestToken(): Promise<any>;
    // (undocumented)
    protected requiredOptions: string[];
}

// @public (undocumented)
export function fileExistsAtPath(filepath: string): boolean;

// @public
export interface FileObject {
    // (undocumented)
    options?: FileOptions;
    // (undocumented)
    value: NodeJS.ReadableStream | Buffer | string;
}

// @public (undocumented)
export interface FileOptions {
    // (undocumented)
    contentType?: string;
    // (undocumented)
    filename?: string;
}

// @public (undocumented)
export interface FileStream extends NodeJS.ReadableStream {
    // (undocumented)
    path: string | Buffer;
}

// @public (undocumented)
export interface FileWithMetadata {
    // (undocumented)
    contentType: string;
    // (undocumented)
    data: NodeJS.ReadableStream | Buffer;
    // (undocumented)
    filename: string;
}

// @public
export function getAuthenticatorFromEnvironment(serviceName: string): Authenticator;

// @public
export function getContentType(inputData: NodeJS.ReadableStream | Buffer): Promise<string>;

// @public
export function getCurrentTime(): number;

// @public
export function getFormat(params: {
    [key: string]: any;
}, formats: string[]): string;

// @public
export function getMissingParams(params: {
    [key: string]: any;
}, requires: string[]): null | Error;

// @public
export function getNewLogger(moduleName: string): SDKLogger;

// @public
export function getQueryParam(urlStr: string, param: string): string;

// Warning: (ae-forgotten-export) The symbol "IamRequestBasedAuthenticatorImmutable" needs to be exported by the entry point index.d.ts
//
// @public
export class IamAssumeAuthenticator extends IamRequestBasedAuthenticatorImmutable {
    // Warning: (ae-forgotten-export) The symbol "Options_16" needs to be exported by the entry point index.d.ts
    constructor(options: Options_16);
    authenticationType(): string;
    // (undocumented)
    protected tokenManager: IamAssumeTokenManager;
}

// @public
export class IamAssumeTokenManager extends IamRequestBasedTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_15" needs to be exported by the entry point index.d.ts
    constructor(options: Options_15);
    protected requestToken(): Promise<any>;
    // (undocumented)
    protected requiredOptions: string[];
    protected saveTokenInfo(tokenResponse: any): void;
    setClientIdAndSecret(clientId: string, clientSecret: string): void;
    setDisableSslVerification(value: boolean): void;
    setHeaders(headers: OutgoingHttpHeaders): void;
    setScope(scope: string): void;
}

// @public
export class IamAuthenticator extends IamRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_6" needs to be exported by the entry point index.d.ts
    constructor(options: Options_6);
    authenticationType(): string;
    getRefreshToken(): string;
    // (undocumented)
    protected requiredOptions: string[];
    // (undocumented)
    protected tokenManager: IamTokenManager;
}

// @public
export class IamRequestBasedAuthenticator extends IamRequestBasedAuthenticatorImmutable {
    setClientIdAndSecret(clientId: string, clientSecret: string): void;
    setDisableSslVerification(value: boolean): void;
    setHeaders(headers: OutgoingHttpHeaders): void;
    setScope(scope: string): void;
}

// @public
export class IamRequestBasedTokenManager extends JwtTokenManager {
    constructor(options: IamRequestOptions);
    // (undocumented)
    protected clientId: string;
    // (undocumented)
    protected clientSecret: string;
    // (undocumented)
    protected formData: any;
    protected isTokenExpired(): boolean;
    // (undocumented)
    protected refreshToken: string;
    protected requestToken(): Promise<any>;
    protected saveTokenInfo(tokenResponse: any): void;
    // (undocumented)
    protected scope: string;
    setClientIdAndSecret(clientId: string, clientSecret: string): void;
    setScope(scope: string): void;
}

// @public
export interface IamRequestOptions extends JwtTokenManagerOptions {
    // (undocumented)
    clientId?: string;
    // (undocumented)
    clientSecret?: string;
    // (undocumented)
    scope?: string;
}

// @public
export class IamTokenManager extends IamRequestBasedTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_5" needs to be exported by the entry point index.d.ts
    constructor(options: Options_5);
    getRefreshToken(): string;
    // (undocumented)
    protected requiredOptions: string[];
}

// @public (undocumented)
export function isEmptyObject(obj: any): boolean;

// @public (undocumented)
export function isFileData(obj: any): obj is NodeJS.ReadableStream | Buffer;

// @public (undocumented)
export function isFileWithMetadata(obj: any): obj is FileWithMetadata;

// @public
export function isHTML(text: string): boolean;

// @public
export function isJsonMimeType(mimeType: string): boolean;

// @public
export class JwtTokenManager extends TokenManager {
    constructor(options: JwtTokenManagerOptions);
    protected requestToken(): Promise<any>;
    protected saveTokenInfo(tokenResponse: any): void;
    // (undocumented)
    protected tokenInfo: any;
    // (undocumented)
    protected tokenName: string;
}

// @public
export type JwtTokenManagerOptions = TokenManagerOptions;

// @public
export class McspAuthenticator extends TokenRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_12" needs to be exported by the entry point index.d.ts
    constructor(options: Options_12);
    authenticationType(): string;
    // (undocumented)
    protected requiredOptions: string[];
    // (undocumented)
    protected tokenManager: McspTokenManager;
}

// @public
export class McspTokenManager extends JwtTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_11" needs to be exported by the entry point index.d.ts
    constructor(options: Options_11);
    // (undocumented)
    protected requestToken(): Promise<any>;
    // (undocumented)
    protected requiredOptions: string[];
}

// @public
export class McspV2Authenticator extends TokenRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_14" needs to be exported by the entry point index.d.ts
    constructor(options: Options_14);
    authenticationType(): string;
    // (undocumented)
    protected tokenManager: McspV2TokenManager;
}

// @public
export class McspV2TokenManager extends JwtTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_13" needs to be exported by the entry point index.d.ts
    constructor(options: Options_13);
    // (undocumented)
    protected requestToken(): Promise<any>;
    // (undocumented)
    protected requiredOptions: string[];
}

// @public
export class NoAuthAuthenticator extends Authenticator {
    // (undocumented)
    authenticate(requestOptions: AuthenticateOptions): Promise<void>;
    authenticationType(): string;
}

// @public
export function onlyOne(...args: any): boolean;

// @public
export const qs: {
    stringify: (queryParams: Object) => string;
};

// @public
export function readCredentialsFile(): any;

// @public (undocumented)
export function readCrTokenFile(filepath: string): string;

// @public
export function readExternalSources(serviceName: string): any;

// @public
export function removeSuffix(str: string, suffix: string): string;

// @public (undocumented)
export interface SDKLogger {
    // (undocumented)
    debug: Debugger;
    // (undocumented)
    error: Debugger;
    // (undocumented)
    info: Debugger;
    // (undocumented)
    verbose: Debugger;
    // (undocumented)
    warn: Debugger;
}

// @public
export function streamToPromise(stream: Stream): Promise<any>;

// @public
export function stripTrailingSlash(url: string): string;

// @public
export class TokenManager {
    constructor(options: TokenManagerOptions);
    // (undocumented)
    protected accessToken: string;
    // (undocumented)
    protected disableSslVerification: boolean;
    // (undocumented)
    protected expireTime: number;
    getToken(): Promise<any>;
    // (undocumented)
    protected headers: OutgoingHttpHeaders;
    protected isTokenExpired(): boolean;
    protected pacedRequestToken(): Promise<any>;
    // (undocumented)
    protected refreshTime: number;
    protected requestToken(): Promise<any>;
    // Warning: (ae-forgotten-export) The symbol "RequestWrapper" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    protected requestWrapperInstance: RequestWrapper;
    protected saveTokenInfo(tokenResponse: any): void;
    setDisableSslVerification(value: boolean): void;
    setHeaders(headers: OutgoingHttpHeaders): void;
    // (undocumented)
    protected url: string;
    // (undocumented)
    protected userAgent: string;
}

// @public
export type TokenManagerOptions = {
    url?: string;
    headers?: OutgoingHttpHeaders;
    disableSslVerification?: boolean;
    [propName: string]: any;
};

// Warning: (ae-forgotten-export) The symbol "TokenRequestBasedAuthenticatorImmutable" needs to be exported by the entry point index.d.ts
//
// @public
export class TokenRequestBasedAuthenticator extends TokenRequestBasedAuthenticatorImmutable {
    setDisableSslVerification(value: boolean): void;
    setHeaders(headers: OutgoingHttpHeaders): void;
}

// @public
export function toLowerKeys(obj: Object): Object;

// @public
export interface UserOptions {
    [propName: string]: any;
    authenticator?: AuthenticatorInterface;
    disableSslVerification?: boolean;
    headers?: OutgoingHttpHeaders;
    jar?: CookieJar | boolean;
    serviceUrl?: string;
    url?: string;
    version?: string;
}

// @public
export function validateInput(options: any, requiredOptions: string[]): void;

// @public
export function validateParams(params: {
    [key: string]: any;
}, requiredParams: string[], allParams: string[]): null | Error;

// @public
export class VpcInstanceAuthenticator extends TokenRequestBasedAuthenticator {
    // Warning: (ae-forgotten-export) The symbol "Options_10" needs to be exported by the entry point index.d.ts
    constructor(options: Options_10);
    authenticationType(): string;
    setIamProfileCrn(iamProfileCrn: string): void;
    setIamProfileId(iamProfileId: string): void;
    // (undocumented)
    protected tokenManager: VpcInstanceTokenManager;
}

// @public
export class VpcInstanceTokenManager extends JwtTokenManager {
    // Warning: (ae-forgotten-export) The symbol "Options_9" needs to be exported by the entry point index.d.ts
    constructor(options: Options_9);
    protected isTokenExpired(): boolean;
    // (undocumented)
    protected requestToken(): Promise<any>;
    setIamProfileCrn(iamProfileCrn: string): void;
    setIamProfileId(iamProfileId: string): void;
}

// (No @packageDocumentation comment for this package)

```
